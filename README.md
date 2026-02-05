# NMR_Assignment_calculator
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
  <meta http-equiv="Content-Style-Type" content="text/css">
  <title></title>
  <meta name="Generator" content="Cocoa HTML Writer">
  <meta name="CocoaVersion" content="2575.7">
  <style type="text/css">
    p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Helvetica}
    p.p2 {margin: 0.0px 0.0px 0.0px 0.0px; font: 12.0px Helvetica; min-height: 14.0px}
  </style>
</head>
<body>
<p class="p1">&lt;!DOCTYPE html&gt;</p>
<p class="p1">&lt;html lang="en"&gt;</p>
<p class="p1">&lt;head&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;meta charset="UTF-8"&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;title&gt;Amino Acid Chemical Shift Predictor&lt;/title&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;style&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>:root {</p>
<p class="p1"><span class="Apple-converted-space">            </span>--primary: #2563eb;</p>
<p class="p1"><span class="Apple-converted-space">            </span>--bg: #f8fafc;</p>
<p class="p1"><span class="Apple-converted-space">            </span>--card: #ffffff;</p>
<p class="p1"><span class="Apple-converted-space">            </span>--text: #1e293b;</p>
<p class="p1"><span class="Apple-converted-space">            </span>--border: #e2e8f0;</p>
<p class="p1"><span class="Apple-converted-space">            </span>--success: #10b981;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>body {</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;</p>
<p class="p1"><span class="Apple-converted-space">            </span>background-color: var(--bg);</p>
<p class="p1"><span class="Apple-converted-space">            </span>color: var(--text);</p>
<p class="p1"><span class="Apple-converted-space">            </span>display: flex;</p>
<p class="p1"><span class="Apple-converted-space">            </span>justify-content: center;</p>
<p class="p1"><span class="Apple-converted-space">            </span>padding: 40px 20px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>margin: 0;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>.container {</p>
<p class="p1"><span class="Apple-converted-space">            </span>background: var(--card);</p>
<p class="p1"><span class="Apple-converted-space">            </span>padding: 2rem;</p>
<p class="p1"><span class="Apple-converted-space">            </span>border-radius: 12px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);</p>
<p class="p1"><span class="Apple-converted-space">            </span>width: 100%;</p>
<p class="p1"><span class="Apple-converted-space">            </span>max-width: 800px;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>h1 {</p>
<p class="p1"><span class="Apple-converted-space">            </span>margin-top: 0;</p>
<p class="p1"><span class="Apple-converted-space">            </span>color: var(--primary);</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-size: 1.5rem;</p>
<p class="p1"><span class="Apple-converted-space">            </span>border-bottom: 2px solid var(--border);</p>
<p class="p1"><span class="Apple-converted-space">            </span>padding-bottom: 1rem;</p>
<p class="p1"><span class="Apple-converted-space">            </span>margin-bottom: 1.5rem;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>.input-group {</p>
<p class="p1"><span class="Apple-converted-space">            </span>display: flex;</p>
<p class="p1"><span class="Apple-converted-space">            </span>gap: 20px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>margin-bottom: 20px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>flex-wrap: wrap;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>.input-wrapper {</p>
<p class="p1"><span class="Apple-converted-space">            </span>flex: 1;</p>
<p class="p1"><span class="Apple-converted-space">            </span>min-width: 200px;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>label {</p>
<p class="p1"><span class="Apple-converted-space">            </span>display: block;</p>
<p class="p1"><span class="Apple-converted-space">            </span>margin-bottom: 8px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-weight: 600;</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-size: 0.9rem;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>input[type="number"] {</p>
<p class="p1"><span class="Apple-converted-space">            </span>width: 100%;</p>
<p class="p1"><span class="Apple-converted-space">            </span>padding: 10px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>border: 1px solid var(--border);</p>
<p class="p1"><span class="Apple-converted-space">            </span>border-radius: 6px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-size: 1rem;</p>
<p class="p1"><span class="Apple-converted-space">            </span>box-sizing: border-box;<span class="Apple-converted-space"> </span></p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>button {</p>
<p class="p1"><span class="Apple-converted-space">            </span>background-color: var(--primary);</p>
<p class="p1"><span class="Apple-converted-space">            </span>color: white;</p>
<p class="p1"><span class="Apple-converted-space">            </span>border: none;</p>
<p class="p1"><span class="Apple-converted-space">            </span>padding: 12px 24px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>border-radius: 6px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>cursor: pointer;</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-size: 1rem;</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-weight: 600;</p>
<p class="p1"><span class="Apple-converted-space">            </span>transition: background 0.2s;</p>
<p class="p1"><span class="Apple-converted-space">            </span>width: 100%;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>button:hover {</p>
<p class="p1"><span class="Apple-converted-space">            </span>background-color: #1d4ed8;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>/* Table Styles */</p>
<p class="p1"><span class="Apple-converted-space">        </span>.table-container {</p>
<p class="p1"><span class="Apple-converted-space">            </span>margin-top: 30px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>overflow-x: auto;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>table {</p>
<p class="p1"><span class="Apple-converted-space">            </span>width: 100%;</p>
<p class="p1"><span class="Apple-converted-space">            </span>border-collapse: collapse;</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-size: 0.95rem;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>th, td {</p>
<p class="p1"><span class="Apple-converted-space">            </span>text-align: left;</p>
<p class="p1"><span class="Apple-converted-space">            </span>padding: 12px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>border-bottom: 1px solid var(--border);</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>th {</p>
<p class="p1"><span class="Apple-converted-space">            </span>background-color: #f1f5f9;</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-weight: 600;</p>
<p class="p1"><span class="Apple-converted-space">            </span>color: #64748b;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>tr:hover {</p>
<p class="p1"><span class="Apple-converted-space">            </span>background-color: #f8fafc;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>/* Probability Bar */</p>
<p class="p1"><span class="Apple-converted-space">        </span>.prob-bar-container {</p>
<p class="p1"><span class="Apple-converted-space">            </span>background-color: #e2e8f0;</p>
<p class="p1"><span class="Apple-converted-space">            </span>border-radius: 4px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>height: 8px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>width: 100px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>display: inline-block;</p>
<p class="p1"><span class="Apple-converted-space">            </span>margin-right: 10px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>vertical-align: middle;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>.prob-bar-fill {</p>
<p class="p1"><span class="Apple-converted-space">            </span>background-color: var(--success);</p>
<p class="p1"><span class="Apple-converted-space">            </span>height: 100%;</p>
<p class="p1"><span class="Apple-converted-space">            </span>border-radius: 4px;</p>
<p class="p1"><span class="Apple-converted-space">            </span>transition: width 0.5s ease-out;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>.highlight {</p>
<p class="p1"><span class="Apple-converted-space">            </span>background-color: #eff6ff;</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-weight: bold;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>.gly-note {</p>
<p class="p1"><span class="Apple-converted-space">            </span>color: #64748b;</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-style: italic;</p>
<p class="p1"><span class="Apple-converted-space">            </span>font-size: 0.85rem;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;/style&gt;</p>
<p class="p1">&lt;/head&gt;</p>
<p class="p1">&lt;body&gt;</p>
<p class="p2"><br></p>
<p class="p1">&lt;div class="container"&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;h1&gt;Amino Acid Predictor&lt;/h1&gt;</p>
<p class="p2"><span class="Apple-converted-space">    </span></p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;p&gt;Enter the Chemical Shift values (ppm) to predict the residue type.&lt;/p&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;div class="input-group"&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;div class="input-wrapper"&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;label for="caInput"&gt;CA Value (Alpha Carbon)&lt;/label&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;input type="number" id="caInput" placeholder="e.g. 56.5" step="0.01"&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;div class="input-wrapper"&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;label for="cbInput"&gt;CB Value (Beta Carbon)&lt;/label&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;input type="number" id="cbInput" placeholder="e.g. 29.1" step="0.01"&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;button onclick="calculatePrediction()"&gt;Predict Residue&lt;/button&gt;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;div class="table-container"&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;table id="resultsTable"&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;thead&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;tr&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;th&gt;Residue&lt;/th&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;th&gt;Probability&lt;/th&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;th&gt;Deviation (ppm)&lt;/th&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/tr&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/thead&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;tbody id="resultsBody"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;tr&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;td colspan="3" style="text-align:center; color: #94a3b8;"&gt;Enter values above to see results&lt;/td&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;/tr&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>&lt;/tbody&gt;</p>
<p class="p1"><span class="Apple-converted-space">        </span>&lt;/table&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>&lt;/div&gt;</p>
<p class="p1">&lt;/div&gt;</p>
<p class="p2"><br></p>
<p class="p1">&lt;script&gt;</p>
<p class="p1"><span class="Apple-converted-space">    </span>// 1. The Amino Acid Database</p>
<p class="p1"><span class="Apple-converted-space">    </span>const aaData = {</p>
<p class="p1"><span class="Apple-converted-space">        </span>'ALA': {'CA': 53.137, 'CB': 19.027},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'ARG': {'CA': 56.757, 'CB': 30.665},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'ASN': {'CA': 53.521, 'CB': 38.706},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'ASP': {'CA': 54.666, 'CB': 40.879},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'CYS': {'CA': 57.976, 'CB': 33.441},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'GLN': {'CA': 56.524, 'CB': 29.170},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'GLU': {'CA': 57.307, 'CB': 29.988},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'HIS': {'CA': 56.485, 'CB': 30.316},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'ILE': {'CA': 61.631, 'CB': 38.553},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'LEU': {'CA': 55.646, 'CB': 42.210},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'LYS': {'CA': 56.940, 'CB': 32.764},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'MET': {'CA': 56.113, 'CB': 32.952},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'PHE': {'CA': 58.100, 'CB': 39.903},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'PRO': {'CA': 63.323, 'CB': 31.873},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'SER': {'CA': 58.671, 'CB': 63.725},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'THR': {'CA': 62.197, 'CB': 69.607},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'TRP': {'CA': 57.732, 'CB': 30.030},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'TYR': {'CA': 58.131, 'CB': 39.267},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'VAL': {'CA': 62.492, 'CB': 32.689},</p>
<p class="p1"><span class="Apple-converted-space">        </span>'GLY': {'CA': 45.362, 'CB': null}</p>
<p class="p1"><span class="Apple-converted-space">    </span>};</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>function calculatePrediction() {</p>
<p class="p1"><span class="Apple-converted-space">        </span>// Get user input</p>
<p class="p1"><span class="Apple-converted-space">        </span>const userCa = parseFloat(document.getElementById('caInput').value);</p>
<p class="p1"><span class="Apple-converted-space">        </span>const userCb = parseFloat(document.getElementById('cbInput').value);</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>if (isNaN(userCa) || isNaN(userCb)) {</p>
<p class="p1"><span class="Apple-converted-space">            </span>alert("Please enter valid numerical values for both CA and CB.");</p>
<p class="p1"><span class="Apple-converted-space">            </span>return;</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>const sigma = 1.5; // Tolerance parameter</p>
<p class="p1"><span class="Apple-converted-space">        </span>let results = [];</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>// 1. Calculate Distances</p>
<p class="p1"><span class="Apple-converted-space">        </span>for (const [aa, values] of Object.entries(aaData)) {</p>
<p class="p1"><span class="Apple-converted-space">            </span>let dist, isGly;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>if (aa === 'GLY') {</p>
<p class="p1"><span class="Apple-converted-space">                </span>// Glycine deviation based on CA only</p>
<p class="p1"><span class="Apple-converted-space">                </span>dist = Math.abs(userCa - values.CA);</p>
<p class="p1"><span class="Apple-converted-space">                </span>isGly = true;</p>
<p class="p1"><span class="Apple-converted-space">            </span>} else {</p>
<p class="p1"><span class="Apple-converted-space">                </span>// Euclidean distance</p>
<p class="p1"><span class="Apple-converted-space">                </span>const dCa = userCa - values.CA;</p>
<p class="p1"><span class="Apple-converted-space">                </span>const dCb = userCb - values.CB;</p>
<p class="p1"><span class="Apple-converted-space">                </span>dist = Math.sqrt(Math.pow(dCa, 2) + Math.pow(dCb, 2));</p>
<p class="p1"><span class="Apple-converted-space">                </span>isGly = false;</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>results.push({</p>
<p class="p1"><span class="Apple-converted-space">                </span>AA: aa,</p>
<p class="p1"><span class="Apple-converted-space">                </span>dist: dist,</p>
<p class="p1"><span class="Apple-converted-space">                </span>isGly: isGly,</p>
<p class="p1"><span class="Apple-converted-space">                </span>likelihood: 0,</p>
<p class="p1"><span class="Apple-converted-space">                </span>prob: 0</p>
<p class="p1"><span class="Apple-converted-space">            </span>});</p>
<p class="p1"><span class="Apple-converted-space">        </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>// 2. Calculate Probabilities (Standard Gaussian)</p>
<p class="p1"><span class="Apple-converted-space">        </span>// Filter out Glycine for probability calculation as per original python logic</p>
<p class="p1"><span class="Apple-converted-space">        </span>const nonGlyResults = results.filter(r =&gt; !r.isGly);</p>
<p class="p1"><span class="Apple-converted-space">        </span>let totalLikelihood = 0;</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>nonGlyResults.forEach(r =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">            </span>const likelihood = Math.exp(-(Math.pow(r.dist, 2)) / (2 * Math.pow(sigma, 2)));</p>
<p class="p1"><span class="Apple-converted-space">            </span>r.likelihood = likelihood;</p>
<p class="p1"><span class="Apple-converted-space">            </span>totalLikelihood += likelihood;</p>
<p class="p1"><span class="Apple-converted-space">        </span>});</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>// Normalize probabilities</p>
<p class="p1"><span class="Apple-converted-space">        </span>nonGlyResults.forEach(r =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">            </span>if (totalLikelihood &gt; 0) {</p>
<p class="p1"><span class="Apple-converted-space">                </span>r.prob = (r.likelihood / totalLikelihood) * 100;</p>
<p class="p1"><span class="Apple-converted-space">            </span>} else {</p>
<p class="p1"><span class="Apple-converted-space">                </span>r.prob = 0.0;</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p1"><span class="Apple-converted-space">        </span>});</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>// Ensure Glycine stays at 0.0 prob (since CB exists)</p>
<p class="p1"><span class="Apple-converted-space">        </span>results.forEach(r =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">            </span>if (r.isGly) r.prob = 0.0;</p>
<p class="p1"><span class="Apple-converted-space">        </span>});</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>// 3. Sort by lowest deviation</p>
<p class="p1"><span class="Apple-converted-space">        </span>results.sort((a, b) =&gt; a.dist - b.dist);</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>renderTable(results);</p>
<p class="p1"><span class="Apple-converted-space">    </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">    </span>function renderTable(predictions) {</p>
<p class="p1"><span class="Apple-converted-space">        </span>const tbody = document.getElementById('resultsBody');</p>
<p class="p1"><span class="Apple-converted-space">        </span>tbody.innerHTML = '';</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">        </span>predictions.forEach((p, index) =&gt; {</p>
<p class="p1"><span class="Apple-converted-space">            </span>const row = document.createElement('tr');</p>
<p class="p2"><span class="Apple-converted-space">            </span></p>
<p class="p1"><span class="Apple-converted-space">            </span>// Highlight the top result</p>
<p class="p1"><span class="Apple-converted-space">            </span>if (index === 0) row.classList.add('highlight');</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>// Format Probability Cell</p>
<p class="p1"><span class="Apple-converted-space">            </span>let probCellContent;</p>
<p class="p1"><span class="Apple-converted-space">            </span>if (p.isGly) {</p>
<p class="p1"><span class="Apple-converted-space">                </span>probCellContent = `&lt;span class="gly-note"&gt;N/A (Has CB)&lt;/span&gt;`;</p>
<p class="p1"><span class="Apple-converted-space">            </span>} else {</p>
<p class="p1"><span class="Apple-converted-space">                </span>// Add a visual bar</p>
<p class="p1"><span class="Apple-converted-space">                </span>const barWidth = p.prob.toFixed(1);</p>
<p class="p1"><span class="Apple-converted-space">                </span>probCellContent = `</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;div style="display: flex; align-items: center;"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;div class="prob-bar-container"&gt;</p>
<p class="p1"><span class="Apple-converted-space">                            </span>&lt;div class="prob-bar-fill" style="width: ${barWidth}%"&gt;&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                        </span>&lt;span&gt;${p.prob.toFixed(2)}%&lt;/span&gt;</p>
<p class="p1"><span class="Apple-converted-space">                    </span>&lt;/div&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>`;</p>
<p class="p1"><span class="Apple-converted-space">            </span>}</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>// Format Deviation Cell</p>
<p class="p1"><span class="Apple-converted-space">            </span>let devText = p.dist.toFixed(3);</p>
<p class="p1"><span class="Apple-converted-space">            </span>if (p.isGly) devText += ' &lt;span class="gly-note"&gt;(CA Only)&lt;/span&gt;';</p>
<p class="p2"><br></p>
<p class="p1"><span class="Apple-converted-space">            </span>row.innerHTML = `</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;td&gt;&lt;strong&gt;${p.AA}&lt;/strong&gt;&lt;/td&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;td&gt;${probCellContent}&lt;/td&gt;</p>
<p class="p1"><span class="Apple-converted-space">                </span>&lt;td&gt;${devText}&lt;/td&gt;</p>
<p class="p1"><span class="Apple-converted-space">            </span>`;</p>
<p class="p2"><span class="Apple-converted-space">            </span></p>
<p class="p1"><span class="Apple-converted-space">            </span>tbody.appendChild(row);</p>
<p class="p1"><span class="Apple-converted-space">        </span>});</p>
<p class="p1"><span class="Apple-converted-space">    </span>}</p>
<p class="p1">&lt;/script&gt;</p>
<p class="p2"><br></p>
<p class="p1">&lt;/body&gt;</p>
<p class="p1">&lt;/html&gt;</p>
</body>
</html>
