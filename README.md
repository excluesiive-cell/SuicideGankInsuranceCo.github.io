# Suicide-Gank-Insurance-Co

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Suicide Gank Insurance Co. [SGICO]</title>
    <style>
        :root {
            --bg-dark: #0a0c10;
            --bg-panel: #141923;
            --border-color: #2a364f;
            --text-main: #e2e8f0;
            --text-muted: #8a99ad;
            --amber-neon: #ff9d00;
            --amber-glow: rgba(255, 157, 0, 0.2);
            --red-alert: #ff3b3b;
            --green-safe: #38a169;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-main);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            overflow-x: hidden;
        }

        body::before {
            content: " ";
            display: block;
            position: fixed;
            top: 0; left: 0; bottom: 0; right: 0;
            background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
            z-index: 99999;
            opacity: 0.3;
            pointer-events: none;
            background-size: 100% 4px, 6px 100%;
        }

        header {
            background-color: var(--bg-panel);
            border-bottom: 2px solid var(--border-color);
            padding: 1.5rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .logo-group h1 {
            font-size: 1.5rem;
            letter-spacing: 2px;
            color: #ffffff;
        }

        .logo-group h1 span {
            color: var(--amber-neon);
            text-shadow: 0 0 10px var(--amber-glow);
        }

        .logo-group p {
            font-size: 0.8rem;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        nav a {
            color: var(--text-main);
            text-decoration: none;
            margin-left: 1.5rem;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--amber-neon);
        }

        .hero {
            padding: 5rem 2rem;
            text-align: center;
            background: radial-gradient(circle at center, #1b2436 0%, var(--bg-dark) 70%);
            border-bottom: 1px solid var(--border-color);
        }

        .hero h2 {
            font-size: 2.8rem;
            margin-bottom: 1rem;
            letter-spacing: 1px;
        }

        .hero p {
            color: var(--text-muted);
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto 2rem auto;
        }

        .container {
            max-width: 1200px;
            margin: 3rem auto;
            padding: 0 2rem;
        }

        h2.section-title {
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 2rem;
            border-left: 4px solid var(--amber-neon);
            padding-left: 1rem;
            font-size: 1.8rem;
        }

        /* Twin Columns for Layout */
        .app-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 3rem;
            margin-bottom: 4rem;
        }

        @media(min-width: 900px) {
            .app-grid {
                grid-template-columns: 1fr 1fr;
            }
        }

        .panel {
            background-color: var(--bg-panel);
            border: 1px solid var(--border-color);
            padding: 2.5rem;
            border-radius: 4px;
            position: relative;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
            text-transform: uppercase;
            color: var(--text-muted);
            font-weight: bold;
            letter-spacing: 1px;
        }

        .form-group select, .form-group input, .form-group textarea {
            width: 100%;
            background-color: var(--bg-dark);
            border: 1px solid var(--border-color);
            color: var(--text-main);
            padding: 0.8rem;
            font-size: 1rem;
            font-family: monospace;
        }

        .form-group textarea {
            height: 220px;
            resize: vertical;
        }

        .form-group select:focus, .form-group input:focus, .form-group textarea:focus {
            outline: none;
            border-color: var(--amber-neon);
            box-shadow: 0 0 5px var(--amber-glow);
        }

        .cta-btn {
            background-color: transparent;
            border: 2px solid var(--amber-neon);
            color: var(--amber-neon);
            padding: 0.8rem 2rem;
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            font-weight: bold;
            cursor: pointer;
            width: 100%;
            box-shadow: 0 0 10px var(--amber-glow);
            transition: all 0.3s ease;
        }

        .cta-btn:hover {
            background-color: var(--amber-neon);
            color: var(--bg-dark);
            box-shadow: 0 0 20px var(--amber-neon);
        }

        /* Results Display */
        .results-box {
            background-color: var(--bg-dark);
            border: 1px dashed var(--border-color);
            padding: 1.5rem;
            margin-top: 1.5rem;
        }

        .summary-row {
            display: flex;
            justify-content: space-between;
            padding: 0.5rem 0;
            border-bottom: 1px solid rgba(42, 54, 79, 0.4);
        }

        .summary-row.total {
            border-bottom: none;
            padding-top: 1rem;
            font-size: 1.3rem;
            font-weight: bold;
            color: var(--amber-neon);
        }

        .breakdown-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1.5rem;
            font-size: 0.85rem;
        }

        .breakdown-table th {
            text-align: left;
            color: var(--text-muted);
            text-transform: uppercase;
            padding: 0.5rem;
            border-bottom: 2px solid var(--border-color);
        }

        .breakdown-table td {
            padding: 0.5rem;
            border-bottom: 1px solid rgba(42, 54, 79, 0.3);
        }

        .risk-tag {
            display: inline-block;
            padding: 0.2rem 0.8rem;
            font-size: 0.8rem;
            text-transform: uppercase;
            font-weight: bold;
            border-radius: 2px;
        }

        footer {
            background-color: #050608;
            border-top: 1px solid var(--border-color);
            padding: 3rem 2rem;
            text-align: center;
            color: var(--text-muted);
            font-size: 0.85rem;
        }
    </style>
</head>
<body>

    <header>
        <div class="logo-group">
            <h1>SUICIDE GANK <span>INSURANCE CO.</span></h1>
            <p>Corporate Suite // Actuarial &amp; Valuation Network</p>
        </div>
        <nav>
            <a href="#appraiser">Janice Bulk Appraiser</a>
            <a href="#risk-calculator">Policy Assessor</a>
            <a href="https://discord.gg/your-link-here" target="_blank" style="color: var(--amber-neon);">Join Discord</a>
        </nav>
    </header>

    <section class="hero">
        <h2>Industrial Evaluation Suite</h2>
        <p>Providing high-sec operations with split-second cargo valuation appraisals alongside standard risk assessment tools.</p>
    </section>

    <div class="container">
        <div class="app-grid">
            
            <div class="panel" id="appraiser">
                <h2 class="section-title">Janice-Style Bulk Appraisal</h2>
                <div class="form-group">
                    <label for="bulkPaste">Paste Inventory / Cargo scan / Contract text</label>
                    <textarea id="bulkPaste" placeholder="Veldspar 45000&#10;Compressed Concentrated Veldspar 1200&#10;Blue Ice 45&#10;Orca 1&#10;Gneiss 8000"></textarea>
                </div>
                <button class="cta-btn" onclick="runAppraisal()">Submit Appraisal</button>

                <div class="results-box" id="appraisalResults" style="display: none;">
                    <div class="summary-row">
                        <span>Total Items Scanned:</span>
                        <span id="appTotalItems" style="font-weight: bold;">0</span>
                    </div>
                    <div class="summary-row">
                        <span>Total Volumetric Size:</span>
                        <span id="appTotalVolume" style="font-weight: bold;">0 m³</span>
                    </div>
                    <div class="summary-row total">
                        <span>Estimated Jita Buy Value:</span>
                        <span id="appTotalValue">0.00 ISK</span>
                    </div>

                    <table class="breakdown-table">
                        <thead>
                            <tr>
                                <th>Item Name</th>
                                <th>Qty</th>
                                <th>Vol (m³)</th>
                                <th>Est Value (ISK)</th>
                            </tr>
                        </thead>
                        <tbody id="breakdownBody">
                            </tbody>
                    </table>
                </div>
            </div>

            <div class="panel" id="risk-calculator">
                <h2 class="section-title">Risk &amp; Policy Underwriter</h2>
                
                <div class="form-group">
                    <label for="shipType">Active Hull Layout</label>
                    <select id="shipType" onchange="calculatePremium()">
                        <option value="barge">Mining Barge (Procurer / Retriever / Covetor)</option>
                        <option value="exmuter">Exmuter / Orca / Rorqual</option>
                        <option value="t1hauler">T1 Industrial Hauler</option>
                        <option value="freighter">Standard Freighter / Bowhead</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="cargoValue">Hangar / Cargo Load Value (ISK Millions)</label>
                    <input type="number" id="cargoValue" value="100" min="0" oninput="calculatePremium()">
                </div>

                <div class="form-group">
                    <label for="spaceRoute">Primary Navigation Chokepoint</label>
                    <select id="spaceRoute" onchange="calculatePremium()">
                        <option value="low">Standard High-Sec Sector (0.7 - 1.0)</option>
                        <option value="med">Minor Transit Pipe (0.5 - 0.6)</option>
                        <option value="high">The Uedama Highway / Main Trade Pipe</option>
                    </select>
                </div>

                <div class="results-box">
                    <div class="summary-row">
                        <span>Risk Threat Matrix:</span>
                        <span id="riskLevel" class="risk-tag">Moderate Risk Profile</span>
                    </div>
                    <div class="summary-row total">
                        <span>Weekly Base Premium:</span>
                        <span id="premiumCost">15,000,000 ISK</span>
                    </div>
                </div>
            </div>

        </div>
    </div>

    <footer>
        <p>&copy; 2026 Suicide Gank Insurance Co. All Systems Operational.</p>
        <p style="font-size: 0.75rem; color: #4a5568; margin-top: 1rem;">Data mappings tracking high-sec minerals, regional gas variants, ice structures, and standard ORE platforms (Miasmos, Kryos, Epithal, Primae, Noctis, Orca, Rorqual, Bowhead, Exmuters). Appraisals track raw market evaluations.</p>
    </footer>

    <script>
        // COMPREHENSIVE REGIONAL EVE PRICING ENGINE (ORES, GAS, ICE, SHIPS)
        const itemDatabase = {
            // --- HIGH SEC ORES ---
            "veldspar": { price: 17, vol: 0.1 }, "concentrated veldspar": { price: 18, vol: 0.1 }, "dense veldspar": { price: 19, vol: 0.1 }, "stable veldspar": { price: 21, vol: 0.1 },
            "scordite": { price: 23, vol: 0.15 }, "condensed scordite": { price: 24, vol: 0.15 }, "massive scordite": { price: 26, vol: 0.15 }, "glossy scordite": { price: 28, vol: 0.15 },
            "pyroxeres": { price: 42, vol: 0.3 }, "solid pyroxeres": { price: 45, vol: 0.3 }, "viscous pyroxeres": { price: 48, vol: 0.3 }, "luminous pyroxeres": { price: 52, vol: 0.3 },
            "plagioclase": { price: 58, vol: 0.35 }, "azure plagioclase": { price: 61, vol: 0.35 }, "rich plagioclase": { price: 65, vol: 0.35 }, "sparkling plagioclase": { price: 70, vol: 0.35 },
            
            // --- LOW SEC ORES ---
            "omber": { price: 85, vol: 0.6 }, "silvery omber": { price: 90, vol: 0.6 }, "golden omber": { price: 98, vol: 0.6 }, "platiniferous omber": { price: 110, vol: 0.6 },
            "jaspet": { price: 120, vol: 2.0 }, "pure jaspet": { price: 130, vol: 2.0 }, "pristine jaspet": { price: 142, vol: 2.0 }, "immaculate jaspet": { price: 160, vol: 2.0 },
            "hemorphite": { price: 195, vol: 3.0 }, "vivid hemorphite": { price: 210, vol: 3.0 }, "radiant hemorphite": { price: 230, vol: 3.0 }, "scintillating hemorphite": { price: 250, vol: 3.0 },
            "hedbergite": { price: 240, vol: 3.0 }, "vitric hedbergite": { price: 260, vol: 3.0 }, "luminous hedbergite": { price: 285, vol: 3.0 }, "glistering hedbergite": { price: 310, vol: 3.0 },

            // --- NULL SEC / W-SPACE ORES ---
            "gneiss": { price: 390, vol: 5.0 }, "iridescent gneiss": { price: 420, vol: 5.0 }, "prismatic gneiss": { price: 450, vol: 5.0 }, "brilliant gneiss": { price: 490, vol: 5.0 },
            "dark ochre": { price: 510, vol: 8.0 }, "onyx ochre": { price: 550, vol: 8.0 }, "obsidian ochre": { price: 600, vol: 8.0 }, "jet ochre": { price: 650, vol: 8.0 },
            "spodumain": { price: 320, vol: 16.0 }, "bright spodumain": { price: 350, vol: 16.0 }, "gleaming spodumain": { price: 380, vol: 16.0 }, "dazzling spodumain": { price: 420, vol: 16.0 },
            "crokite": { price: 950, vol: 16.0 }, "sharp crokite": { price: 1020, vol: 16.0 }, "crystalline crokite": { price: 1100, vol: 16.0 }, "pellucid crokite": { price: 1250, vol: 16.0 },
            "bistot": { price: 1100, vol: 16.0 }, "triclinic bistot": { price: 1200, vol: 16.0 }, "monoclinic bistot": { price: 1350, vol: 16.0 }, "cubic bistot": { price: 1500, vol: 16.0 },
            "arkonor": { price: 1400, vol: 16.0 }, "crimson arkonor": { price: 1550, vol: 16.0 }, "prime arkonor": { price: 1700, vol: 16.0 }, "flawless arkonor": { price: 1900, vol: 16.0 },
            "mercoxit": { price: 2800, vol: 40.0 }, "magma mercoxit": { price: 3100, vol: 40.0 }, "vitreous mercoxit": { price: 3400, vol: 40.0 },

            // --- POCHVEN / ABOYSMAL ORES ---
            "beidellite": { price: 1800, vol: 3.0 }, "talassonite": { price: 2200, vol: 5.0 }, "raakovite": { price: 3500, vol: 8.0 },

            // --- ICE HARVESTS ---
            "blue ice": { price: 180000, vol: 1000.0 }, "clear icicle": { price: 185000, vol: 1000.0 }, "glacial mass": { price: 190000, vol: 1000.0 }, "white glaze": { price: 210000, vol: 1000.0 },
            "krystallos": { price: 320000, vol: 1000.0 }, "gelidus": { price: 340000, vol: 1000.0 }, "dark glitter": { price: 410000, vol: 1000.0 }, "en परिस्थिति ice": { price: 390000, vol: 1000.0 },

            // --- GAS CLOUDS (FULLERENES & CYTOSEROCIN) ---
            "c320": { price: 95000, vol: 5.0 }, "c540": { price: 120000, vol: 10.0 }, "c100": { price: 15000, vol: 1.0 }, "c50": { price: 8000, vol: 1.0 }, "c28": { price: 11000, vol: 1.0 },
            "c72": { price: 22000, vol: 2.0 }, "c84": { price: 28000, vol: 2.0 }, "c60": { price: 6000, vol: 1.0 }, "amber cytoserocin": { price: 45000, vol: 10.0 },
            "golden cytoserocin": { price: 65000, vol: 10.0 }, "viridian cytoserocin": { price: 35000, vol: 10.0 }, "lime cytoserocin": { price: 55000, vol: 10.0 },

            // --- ORE SHIPYARD PLATFORMS ---
            "venture": { price: 450000, vol: 2500 },
            "procurer": { price: 38000000, vol: 20000 }, "retriever": { price: 42000000, vol: 20000 }, "covetor": { price: 48000000, vol: 20000 },
            "skiff": { price: 280000000, vol: 20000 }, "mackinaw": { price: 290000000, vol: 20000 }, "hulk": { price: 310000000, vol: 20000 },
            "miasmos": { price: 1200000, vol: 20000 }, "kryos": { price: 1200000, vol: 20000 }, "epithal": { price: 1200000, vol: 20000 }, 
            "primae": { price: 15000000, vol: 20000 }, "noctis": { price: 75000000, vol: 20000 }, "porpoise": { price: 85000000, vol: 50000 },
            "orca": { price: 1100000000, vol: 500000 }, "rorqual": { price: 3400000000, vol: 1000000 }, "bowhead": { price: 1300000000, vol: 1300000 }
        };

        // Add auto-generated compressed values to the map
        Object.keys(itemDatabase).forEach(key => {
            if (itemDatabase[key].vol <= 40 && !key.includes("cytoserocin") && !key.startsWith("c")) {
                itemDatabase["compressed " + key] = {
                    price: itemDatabase[key].price * 100, 
                    vol: parseFloat((itemDatabase[key].vol * 1.0).toFixed(2))
                };
            }
        });

        function runAppraisal() {
            const rawText = document.getElementById("bulkPaste").value;
            const lines = rawText.split('\n');
            
            let totalItems = 0;
            let totalVolume = 0;
            let totalValue = 0;
            
            const tbody = document.getElementById("breakdownBody");
            tbody.innerHTML = "";

            lines.forEach(line => {
                if (!line.trim()) return;

                let cleanLine = line.replace(/,/g, '').replace(/\t/g, ' ').trim();
                let tokens = cleanLine.split(/\s+/);
                
                let qty = 1;
                let nameTokens = [...tokens];
                
                if (tokens.length > 1) {
                    let lastToken = tokens[tokens.length - 1];
                    if (!isNaN(lastToken)) {
                        qty = parseInt(lastToken);
                        nameTokens.pop();
                    }
                }
                
                let itemName = nameTokens.join(' ').toLowerCase().trim();
                
                if (itemDatabase[itemName]) {
                    let data = itemDatabase[itemName];
                    let lineVol = data.vol * qty;
                    let lineValue = data.price * qty;
                    
                    totalItems += qty;
                    totalVolume += lineVol;
                    totalValue += lineValue;

                    let row = `<tr>
                        <td style="text-transform: capitalize; font-weight: bold;">${itemName}</td>
                        <td>${qty.toLocaleString()}</td>
                        <td>${lineVol.toLocaleString(undefined, {maximumFractionDigits: 1})}</td>
                        <td style="color: #cbd5e1;">${lineValue.toLocaleString()} ISK</td>
                    </tr>`;
                    tbody.innerHTML += row;
                }
            });

            document.getElementById("appTotalItems").innerText = totalItems.toLocaleString();
            document.getElementById("appTotalVolume").innerText = totalVolume.toLocaleString(undefined, {maximumFractionDigits: 1}) + " m³";
            document.getElementById("appTotalValue").innerText = totalValue.toLocaleString(undefined, {maximumFractionDigits: 2}) + " ISK";
            document.getElementById("appraisalResults").style.display = "block";
        }

        function calculatePremium() {
            const shipType = document.getElementById('shipType').value;
            const cargoValue = parseFloat(document.getElementById('cargoValue').value) || 0;
            const spaceRoute = document.getElementById('spaceRoute').value;

            let baseRate = 5000000;
            let riskMultiplier = 1.0;

            if (shipType === 'barge') baseRate = 8000000;
            if (shipType === 'exmuter') baseRate = 25000000;
            if (shipType === 't1hauler') baseRate = 4000000;
            if (shipType === 'freighter') baseRate = 45000000;

            let cargoFee = cargoValue * 150000;
            let riskText = "Moderate Risk Profile";
            let riskColor = "#e28743";
            let riskTextCol = "#000000";

            if (spaceRoute === 'low') {
                riskMultiplier = 0.8;
                riskText = "Low Risk Profile";
                riskColor = "var(--green-safe)";
                riskTextCol = "#ffffff";
            } else if (spaceRoute === 'med') {
                riskMultiplier = 1.2;
                riskText = "Elevated Risk Profile";
                riskColor = "#dd6b20";
                riskTextCol = "#ffffff";
            } else if (spaceRoute === 'high') {
                riskMultiplier = 2.5;
                riskText = "CRITICAL CHOKEPOINT RISK (GANK MAGNET)";
                riskColor = "var(--red-alert)";
                riskTextCol = "#ffffff";
            }

            let totalPremium = (baseRate + cargoFee) * riskMultiplier;
            let formattedPremium = totalPremium >= 1000000 ? (totalPremium / 1000000).toFixed(1) + " Million ISK" : (totalPremium / 1000).toFixed(0) + ",000 ISK";
            document.getElementById('premiumCost').innerText = formattedPremium;
            
            const tag = document.getElementById('riskLevel');
            tag.innerText = riskText;
            tag.style.backgroundColor = riskColor;
            tag.style.color = riskTextCol;
        }

        // Run default state calculation
        calculatePremium();
    </script>
</body>
</html>
