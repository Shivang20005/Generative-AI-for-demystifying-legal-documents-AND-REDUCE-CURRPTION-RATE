# Generative-AI-for-demystifying-legal-documents-AND-REDUCE-CURRPTION-RATE
The prototype is an AI-powered platform designed not only to simplify legal documents but also to promote transparency in governance. Along with document upload and plain-language explanations, the interface includes a section where higher authorities can post Government Orders (G.O.s) and fund allocations.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>AI for Legal Clarity & Governance Transparency</title>
  <style>
    body { font-family: Arial, sans-serif; background:#f9fafb; margin:0; padding:20px; }
    h1 { text-align:center; color:#1e40af; }
    .container { display:grid; grid-template-columns:1fr 1fr; gap:20px; margin-top:20px; }
    .card { background:#fff; border-radius:12px; padding:20px; box-shadow:0 2px 8px rgba(0,0,0,0.1); }
    textarea, input, select { width:100%; padding:10px; margin:10px 0; border:1px solid #ccc; border-radius:8px; }
    button { background:#2563eb; color:#fff; padding:10px 16px; border:none; border-radius:8px; cursor:pointer; }
    button:hover { background:#1e40af; }
    .output { margin-top:10px; padding:12px; border-radius:10px; }
    .green { background:#ecfdf5; border:1px solid #10b981; }
    .blue { background:#eff6ff; border:1px solid #3b82f6; }
    .yellow { background:#fefce8; border:1px solid #eab308; }
  </style>
</head>
<body>

  <h1>AI for Legal Clarity & Governance Transparency</h1>

  <div class="container">
    <!-- Legal Simplification -->
    <div class="card">
      <h2>📄 Document Upload & Simplification</h2>
      <textarea id="documentInput" rows="6" placeholder="Paste your legal document here..."></textarea>
      <button onclick="simplify()">Simplify</button>
      <div id="simplifiedOutput" class="output green" style="display:none;"></div>
    </div>

    <!-- Q&A -->
    <div class="card">
      <h2>🤖 Ask AI</h2>
      <input id="queryInput" type="text" placeholder="Ask a question about a clause...">
      <button onclick="ask()">Get Answer</button>
      <div id="answerOutput" class="output blue" style="display:none;"></div>
    </div>
  </div>

  <!-- Transparency -->
  <div class="card" style="margin-top:20px;">
    <h2>📊 Governance Transparency</h2>
    <select id="areaSelect" onchange="updateTransparency()">
      <option>Delhi</option>
      <option>Mumbai</option>
      <option>Lucknow</option>
    </select>
    <div id="transparencyOutput" class="output yellow" style="margin-top:10px;"></div>
  </div>

  <script>
    function simplify() {
      const doc = document.getElementById("documentInput").value.trim();
      const output = document.getElementById("simplifiedOutput");
      if (doc) {
        output.style.display = "block";
        output.innerText = "Simplified: This document ensures transparency and citizen rights. (Demo Output)";
      }
    }

    function ask() {
      const query = document.getElementById("queryInput").value.trim();
      const output = document.getElementById("answerOutput");
      if (query) {
        output.style.display = "block";
        output.innerText = "AI Answer: Based on your query, this clause supports citizens’ rights. (Demo Output)";
      }
    }

    function updateTransparency() {
      const area = document.getElementById("areaSelect").value;
      const output = document.getElementById("transparencyOutput");
      let data = {
        "Delhi": { go: "Road Development Order 2025", fund: "₹10 Cr allocated" },
        "Mumbai": { go: "Water Supply Improvement G.O.", fund: "₹15 Cr allocated" },
        "Lucknow": { go: "Smart City Housing G.O.", fund: "₹8 Cr allocated" }
      };
      output.innerHTML = `<p><strong>Government Order:</strong> ${data[area].go}</p>
                          <p><strong>Fund Allocation:</strong> ${data[area].fund}</p>`;
    }

    // Initialize with Delhi
    updateTransparency();
  </script>

</body>
</html>
