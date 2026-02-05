# NMR_Assignment_calculator
import math

def get_amino_acid_data():
    """
    Returns the dictionary of Amino Acid chemical shifts.
    """
    return {
        'ALA': {'CA': 53.137, 'CB': 19.027},
        'ARG': {'CA': 56.757, 'CB': 30.665},
        'ASN': {'CA': 53.521, 'CB': 38.706},
        'ASP': {'CA': 54.666, 'CB': 40.879},
        'CYS': {'CA': 57.976, 'CB': 33.441},
        'GLN': {'CA': 56.524, 'CB': 29.170},
        'GLU': {'CA': 57.307, 'CB': 29.988},
        'HIS': {'CA': 56.485, 'CB': 30.316},
        'ILE': {'CA': 61.631, 'CB': 38.553},
        'LEU': {'CA': 55.646, 'CB': 42.210},
        'LYS': {'CA': 56.940, 'CB': 32.764},
        'MET': {'CA': 56.113, 'CB': 32.952},
        'PHE': {'CA': 58.100, 'CB': 39.903},
        'PRO': {'CA': 63.323, 'CB': 31.873},
        'SER': {'CA': 58.671, 'CB': 63.725},
        'THR': {'CA': 62.197, 'CB': 69.607},
        'TRP': {'CA': 57.732, 'CB': 30.030},
        'TYR': {'CA': 58.131, 'CB': 39.267},
        'VAL': {'CA': 62.492, 'CB': 32.689},
        'GLY': {'CA': 45.362, 'CB': None}   # Glycine has no Beta Carbon
    }

def calculate_prediction(user_ca, user_cb):
    data = get_amino_acid_data()
    results = []
    sigma = 1.5  # Tolerance parameter (ppm)
    
    # 1. Calculate Distances
    for aa, values in data.items():
        if aa == 'GLY':
            # Glycine deviation is based on CA only
            dist = abs(user_ca - values['CA'])
            results.append({
                'AA': aa,
                'dist': dist,
                'is_gly': True
            })
        else:
            # 2D Euclidean distance for others
            d_ca = user_ca - values['CA']
            d_cb = user_cb - values['CB']
            dist = math.sqrt(d_ca**2 + d_cb**2)
            results.append({
                'AA': aa,
                'dist': dist,
                'is_gly': False
            })

    # 2. Calculate Probabilities (Standard Gaussian distribution)
    # We only calculate probability % for the 19 residues that have both CA/CB.
    non_gly_results = [r for r in results if not r['is_gly']]
    total_likelihood = 0
    
    for r in non_gly_results:
        likelihood = math.exp(-(r['dist']**2) / (2 * sigma**2))
        r['likelihood'] = likelihood
        total_likelihood += likelihood
        
    for r in non_gly_results:
        if total_likelihood > 0:
            r['prob'] = (r['likelihood'] / total_likelihood) * 100
        else:
            r['prob'] = 0.0

    # For Glycine, we set probability to 0.0 for list sorting purposes
    # (since having a CB value usually rules out Glycine)
    for r in results:
        if r['is_gly']:
            r['prob'] = 0.0

    # 3. Sort ALL results by lowest deviation (best match)
    results.sort(key=lambda x: x['dist'])

    return results

def main():
    print("--- Amino Acid Predictor ---")
    try:
        user_ca = float(input("Enter CA value: "))
        user_cb = float(input("Enter CB value: "))
        
        predictions = calculate_prediction(user_ca, user_cb)
        
        print("\n{:<5} | {:<12} | {:<15}".format("AA", "Probability", "Deviation"))
        print("-" * 40)
        
        for p in predictions:
            if p['is_gly']:
                # Special print for Glycine
                print("{:<5} | {:<12} | {:<10.3f} (CA Only)".format(p['AA'], "N/A", p['dist']))
            else:
                print("{:<5} | {:<11.4f}% | {:<10.3f}".format(p['AA'], p['prob'], p['dist']))

    except ValueError:
        print("Error: Please enter valid numerical values.")

if __name__ == "__main__":
    main()
