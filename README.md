# GSR-Oakbrook
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2025 U.S. Mobile Carrier Market: An Infographic</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700;900&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #eef4f4;
            color: #001219;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            height: 350px;
            max-height: 450px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 400px;
            }
        }
        .kpi {
            background-color: #005f73;
            color: #ffffff;
        }
        .card {
            background-color: #ffffff;
            border: 1px solid #cae9ff;
        }
        .flow-line {
            width: 2px;
            background-color: #94d2bd;
            flex-grow: 1;
        }
        .flow-box {
            border: 2px solid #0a9396;
            background-color: white;
        }
        .flow-box-mvno {
             border: 2px dashed #94d2bd;
             background-color: #f8f9fa;
        }
    </style>
</head>
<body class="antialiased">
    <!-- 
        Narrative Plan:
        1.  Introduction: Hook with market complexity.
        2.  Market Structure: Visualize the MNO -> Flanker/MVNO hierarchy.
        3.  Price Comparison: Bar chart for single-line flagship plans.
        4.  Data Deep Dive: Bar chart for premium data, KPI for hotspot leaders.
        5.  Family Value: Bar chart for 4-line budget plans.
        6.  International Features: Donut chart for roaming models, icons for calling leaders.
        7.  Hidden Costs: Bar chart for activation fees.
        8.  Recommendations: Icon-based cards for user profiles.

        Visualization Choices:
        - Market Structure: HTML/CSS Flowchart. Goal: Organize/Relationships. Justification: No SVG/Mermaid allowed.
        - Price/Data/Family/Fees Charts: Chart.js Bar Chart. Goal: Compare. Justification: Best for comparing metrics across categories.
        - Hotspot Data: Big Number KPI. Goal: Inform. Justification: Highlighting standout numbers.
        - Roaming Models: Chart.js Donut Chart. Goal: Compare/Inform. Justification: Shows composition of the market.
        - Recommendations/Int'l Calling: HTML/CSS with Unicode Icons. Goal: Organize/Inform. Justification: Visually engaging, no SVG allowed.
        - All charts use Canvas rendering via Chart.js.

        Color Palette: Brilliant Blues
        
        NO SVG was used in this document.
        NO MERMAID JS was used in this document.
    -->
    <div class="container mx-auto p-4 md:p-8">

        <header class="text-center mb-12">
            <h1 class="text-4xl md:text-5xl font-black text-[#005f73] mb-2">The 2025 U.S. Wireless Market</h1>
            <p class="text-lg md:text-xl text-[#001219] max-w-3xl mx-auto">Navigating a complex landscape of providers, plans, and priorities to find your perfect match.</p>
        </header>

        <section id="market-structure" class="mb-16">
            <div class="text-center mb-8 max-w-3xl mx-auto">
                <h2 class="text-3xl font-bold text-[#005f73] mb-2">Understanding the Wireless Battlefield</h2>
                <p class="text-md text-[#001219]">The U.S. mobile market is a three-tiered system. At the top are Major Network Operators (MNOs) who own the cell towers. They lease access to MNO-owned "Flanker" brands and independent Mobile Virtual Network Operators (MVNOs). This hierarchy directly impacts your cost and, critically, your data priority during network congestion.</p>
            </div>
            <div class="w-full p-6 card rounded-lg shadow-lg">
                 <div class="flex flex-col items-center">
                    <div class="grid grid-cols-2 lg:grid-cols-4 gap-4 w-full text-center">
                        <div class="p-4 flow-box rounded-lg shadow"><span class="font-bold text-lg">AT&T</span><br><span class="text-sm">(MNO)</span></div>
                        <div class="p-4 flow-box rounded-lg shadow"><span class="font-bold text-lg">Verizon</span><br><span class="text-sm">(MNO)</span></div>
                        <div class="p-4 flow-box rounded-lg shadow"><span class="font-bold text-lg">T-Mobile</span><br><span class="text-sm">(MNO)</span></div>
                        <div class="p-4 flow-box rounded-lg shadow"><span class="font-bold text-lg">U.S. Cellular</span><br><span class="text-sm">(MNO)</span></div>
                    </div>
                    <div class="h-8 w-px bg-[#94d2bd] my-2"></div>
                    <div class="text-[#0a9396] font-semibold mb-2">▼ LEASE NETWORK TO ▼</div>
                    <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 w-full text-center">
                        <div class="p-3 flow-box-mvno rounded-lg">Visible <span class="text-xs block">(from Verizon)</span></div>
                        <div class="p-3 flow-box-mvno rounded-lg">Metro <span class="text-xs block">(from T-Mobile)</span></div>
                        <div class="p-3 flow-box-mvno rounded-lg">Total <span class="text-xs block">(from Verizon)</span></div>
                        <div classp-3 flow-box-mvno rounded-lg">Google Fi <span class="text-xs block">(from T-Mobile)</span></div>
                        <div class="p-3 flow-box-mvno rounded-lg">Mint Mobile <span class="text-xs block">(from T-Mobile)</span></div>
                        <div class="p-3 flow-box-mvno rounded-lg">Ultra Mobile <span class="text-xs block">(from T-Mobile)</span></div>
                        <div class="p-3 flow-box-mvno rounded-lg">Lyca Mobile <span class="text-xs block">(from T-Mobile)</span></div>
                        <div class="p-3 flow-box-mvno rounded-lg">Boost Mobile <span class="text-xs block">(uses AT&T, T-Mobile & own network)</span></div>
                    </div>
                 </div>
            </div>
        </section>
        
        <section id="price-showdown" class="mb-16">
            <div class="text-center mb-8 max-w-3xl mx-auto">
                <h2 class="text-3xl font-bold text-[#005f73] mb-2">The Price of Power: Single-Line Showdown</h2>
                <p class="text-md text-[#001219]">This is the monthly cost for each carrier's top-tier, flagship unlimited plan for a single line. While MNOs offer the most features, their flanker and MVNO competitors provide significant savings for those who don't need every bell and whistle.</p>
            </div>
            <div class="card rounded-lg shadow-lg p-4 md:p-6">
                <div class="chart-container">
                    <canvas id="singleLinePriceChart"></canvas>
                </div>
            </div>
        </section>

        <section id="data-delusion" class="mb-16">
            <div class="text-center mb-8 max-w-3xl mx-auto">
                <h2 class="text-3xl font-bold text-[#005f73] mb-2">The "Unlimited" Data Delusion</h2>
                <p class="text-md text-[#001219]">"Unlimited" rarely means unlimited. Most plans offer a set amount of "premium" data. Exceed it, and you may be temporarily slowed down (deprioritized) when the network is busy, or permanently slowed (throttled) for the rest of the month. Only a select few offer truly unlimited premium data.</p>
            </div>
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                <div class="lg:col-span-2 card rounded-lg shadow-lg p-4 md:p-6">
                    <h3 class="text-xl font-bold text-center mb-4 text-[#005f73]">Premium Data Before Slowdown (GB)</h3>
                     <div class="chart-container h-[400px] md:h-[450px]">
                        <canvas id="premiumDataChart"></canvas>
                    </div>
                </div>
                <div class="flex flex-col gap-8">
                    <div class="kpi rounded-lg shadow-lg p-6 text-center flex flex-col justify-center h-full">
                        <h3 class="text-lg font-bold text-[#e9d8a6] mb-2">Hotspot Data Leaders</h3>
                        <div class="text-5xl font-black text-white">250 <span class="text-3xl">GB</span></div>
                        <p class="font-semibold mt-1">on T-Mobile</p>
                        <div class="text-4xl font-black text-white mt-4">200 <span class="text-2xl">GB</span></div>
                        <p class="font-semibold mt-1">on Verizon</p>
                        <p class="text-sm mt-4 text-[#94d2bd]">Top MNO plans provide massive hotspot allowances, turning your phone into a powerful mobile office.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="family-value" class="mb-16">
            <div class="text-center mb-8 max-w-3xl mx-auto">
                <h2 class="text-3xl font-bold text-[#005f73] mb-2">The Family Value Equation</h2>
                <p class="text-md text-[#001219]">For families, the per-line cost is paramount. The greatest savings are found with MVNOs and flanker brands that offer aggressive multi-line discounts, often cutting the cost per person by more than half compared to single-line MNO plans.</p>
            </div>
            <div class="card rounded-lg shadow-lg p-4 md:p-6">
                <h3 class="text-xl font-bold text-center mb-4 text-[#005f73]">Best Value: Per-Line Cost on a 4-Line Family Plan</h3>
                <div class="chart-container">
                    <canvas id="familyPlanChart"></canvas>
                </div>
            </div>
        </section>

        <section id="international" class="mb-16">
            <div class="text-center mb-8 max-w-3xl mx-auto">
                <h2 class="text-3xl font-bold text-[#005f73] mb-2">The Globetrotter's Guide</h2>
                <p class="text-md text-[#001219]">International features vary dramatically. Some carriers are built for calling other countries *from* the U.S., while others excel at providing affordable data *while you are abroad*. Choosing the wrong plan can lead to staggering fees.</p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="card rounded-lg shadow-lg p-4 md:p-6">
                    <h3 class="text-xl font-bold text-center mb-4 text-[#005f73]">International Roaming Models</h3>
                    <div class="chart-container h-[300px] md:h-auto">
                        <canvas id="roamingModelChart"></canvas>
                    </div>
                     <p class="text-center text-sm mt-4 text-[#001219]">Most carriers use a costly daily "Pass" system for international data. T-Mobile and Google Fi are outliers, integrating generous data into their top plans for superior value.</p>
                </div>
                <div class="card rounded-lg shadow-lg p-6 flex flex-col justify-center items-center text-center">
                     <h3 class="text-xl font-bold text-[#005f73] mb-4">Best for Calling <span class="text-[#0a9396]">From</span> the U.S.</h3>
                     <div class="text-6xl mb-4">🌐</div>
                     <p class="text-lg font-semibold">Ultra Mobile & Lyca Mobile</p>
                     <p class="text-md mt-2 text-[#001219]">These carriers are the undisputed champions for making international calls. Their plans include unlimited calling to <span class="font-bold text-[#005f73]">80-100+ countries</span> as a standard feature, a perk that costs extra on almost every other carrier.</p>
                </div>
            </div>
        </section>

        <section id="hidden-costs" class="mb-16">
            <div class="text-center mb-8 max-w-3xl mx-auto">
                <h2 class="text-3xl font-bold text-[#005f73] mb-2">Decoding the Bill: The Hidden Cost of Activation</h2>
                <p class="text-md text-[#001219]">One of the biggest "gotchas" in mobile plans is the one-time activation or upgrade fee charged per line. MNOs and some of their partners rely on these fees, while most all-digital MVNOs have eliminated them entirely as a competitive advantage.</p>
            </div>
            <div class="card rounded-lg shadow-lg p-4 md:p-6">
                 <h3 class="text-xl font-bold text-center mb-4 text-[#005f73]">Typical Per-Line Activation & Upgrade Fees</h3>
                <div class="chart-container">
                    <canvas id="activationFeeChart"></canvas>
                </div>
            </div>
        </section>
        
        <section id="recommendations">
             <div class="text-center mb-8 max-w-3xl mx-auto">
                <h2 class="text-3xl font-bold text-[#005f73] mb-2">Find Your Perfect Match</h2>
                <p class="text-md text-[#001219]">The best carrier isn't universal—it's the one that fits your specific needs and budget. Here are the top picks for common user profiles based on this analysis.</p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div class="card rounded-lg shadow-lg p-6 text-center">
                    <div class="text-5xl mb-3">💼</div>
                    <h3 class="text-xl font-bold text-[#005f73] mb-2">The Power User</h3>
                    <p class="font-bold text-lg mb-2">Verizon or AT&T</p>
                    <p class="text-sm">For those who need uncompromising performance, their top plans offer truly unlimited premium data and the largest hotspot allowances, ensuring you're never slowed down.</p>
                </div>
                 <div class="card rounded-lg shadow-lg p-6 text-center">
                    <div class="text-5xl mb-3">👨‍👩‍👧‍👦</div>
                    <h3 class="text-xl font-bold text-[#005f73] mb-2">The Budget Family</h3>
                    <p class="font-bold text-lg mb-2">Mint or Visible+</p>
                    <p class="text-sm">Mint Mobile's bulk-pricing delivers the lowest monthly cost, while Visible+ offers an incredible value with premium data on the Verizon network for a simple, all-in price.</p>
                </div>
                 <div class="card rounded-lg shadow-lg p-6 text-center">
                    <div class="text-5xl mb-3">✈️</div>
                    <h3 class="text-xl font-bold text-[#005f73] mb-2">The Int'l Traveler</h3>
                    <p class="font-bold text-lg mb-2">Google Fi or T-Mobile</p>
                    <p class="text-sm">These two are in a class of their own, including huge amounts of high-speed data for use in 200+ countries, saving frequent travelers hundreds over "Day Pass" plans.</p>
                </div>
                 <div class="card rounded-lg shadow-lg p-6 text-center">
                    <div class="text-5xl mb-3">💸</div>
                    <h3 class="text-xl font-bold text-[#005f73] mb-2">The Light User</h3>
                    <p class="font-bold text-lg mb-2">Mint or Google Fi Flexible</p>
                    <p class="text-sm">For those primarily on Wi-Fi, Mint's 5GB plan or Fi's pay-per-gigabyte Flexible plan offer rock-bottom prices without paying for data you don't need.</p>
                </div>
                 <div class="card rounded-lg shadow-lg p-6 text-center">
                    <div class="text-5xl mb-3">🗣️</div>
                    <h3 class="text-xl font-bold text-[#005f73] mb-2">The Int'l Caller</h3>
                    <p class="font-bold text-lg mb-2">Ultra or Lyca Mobile</p>
                    <p class="text-sm">Purpose-built for calling abroad from the U.S., these MVNOs include unlimited calls to 80-100+ countries in their plans, offering far superior value than MNO add-ons.</p>
                </div>
                 <div class="card rounded-lg shadow-lg p-6 text-center">
                    <div class="text-5xl mb-3">✨</div>
                    <h3 class="text-xl font-bold text-[#005f73] mb-2">The Simplicity Seeker</h3>
                    <p class="font-bold text-lg mb-2">Visible</p>
                    <p class="text-sm">With taxes and fees included in the advertised price, no activation fees, and simple plan structures, Visible offers the most transparent and predictable billing in the market.</p>
                </div>
            </div>
        </section>

    </div>

    <script>
        const brilliantBlues = {
            primary: '#005f73',
            secondary: '#0a9396',
            accent: '#94d2bd',
            highlight: '#e9d8a6',
            light: '#cae9ff',
            dark: '#001219',
        };

        const chartDefaultOptions = {
            responsive: true,
            maintainAspectRatio: false,
            plugins: {
                legend: {
                    display: false
                },
                tooltip: {
                    enabled: true,
                    mode: 'index',
                    intersect: false,
                    backgroundColor: 'rgba(0, 18, 25, 0.85)',
                    titleFont: {
                        size: 14,
                        weight: 'bold'
                    },
                    bodyFont: {
                        size: 12
                    },
                    padding: 10,
                    cornerRadius: 4,
                    callbacks: {
                        title: function(tooltipItems) {
                            const item = tooltipItems[0];
                            let label = item.chart.data.labels[item.dataIndex];
                            if (Array.isArray(label)) {
                                return label.join(' ');
                            }
                            return label;
                        }
                    }
                }
            },
            scales: {
                x: {
                    ticks: {
                        color: brilliantBlues.dark,
                        font: {
                           size: 11
                        }
                    },
                    grid: {
                        display: false
                    }
                },
                y: {
                    ticks: {
                        color: brilliantBlues.dark,
                         callback: function(value, index, values) {
                            return '$' + value;
                        }
                    },
                    grid: {
                        color: '#e0e0e0',
                        borderDash: [2, 4],
                    }
                }
            }
        };

        function wrapLabel(str, maxLen = 16) {
            if (str.length <= maxLen) {
                return str;
            }
            const words = str.split(' ');
            let lines = [];
            let currentLine = '';
            for (const word of words) {
                if ((currentLine + ' ' + word).length > maxLen && currentLine.length > 0) {
                    lines.push(currentLine);
                    currentLine = word;
                } else {
                    if(currentLine.length > 0) currentLine += ' ';
                    currentLine += word;
                }
            }
            lines.push(currentLine);
            return lines;
        }

        const createChart = (ctx, type, data, options) => {
            new Chart(ctx, { type, data, options });
        };

        document.addEventListener('DOMContentLoaded', () => {
            const singleLinePriceCtx = document.getElementById('singleLinePriceChart').getContext('2d');
            const premiumDataCtx = document.getElementById('premiumDataChart').getContext('2d');
            const familyPlanCtx = document.getElementById('familyPlanChart').getContext('2d');
            const roamingModelCtx = document.getElementById('roamingModelChart').getContext('2d');
            const activationFeeCtx = document.getElementById('activationFeeChart').getContext('2d');
            
            const singleLinePriceData = {
                labels: ['Visible+', 'Mint', 'U.S. Cellular', 'Google Fi', 'AT&T', 'Verizon', 'T-Mobile'].map(l => wrapLabel(l)),
                datasets: [{
                    label: 'Cost per Month',
                    data: [35, 20, 50, 65, 85.99, 100, 100],
                    backgroundColor: [brilliantBlues.accent, brilliantBlues.highlight, brilliantBlues.secondary, brilliantBlues.secondary, brilliantBlues.primary, brilliantBlues.primary, brilliantBlues.primary],
                    borderColor: brilliantBlues.dark,
                    borderWidth: 0,
                    borderRadius: 5,
                }]
            };
            createChart(singleLinePriceCtx, 'bar', singleLinePriceData, { ...chartDefaultOptions });
            
            const premiumDataOptions = JSON.parse(JSON.stringify(chartDefaultOptions));
            premiumDataOptions.scales.y.ticks.callback = (value) => value === 175 ? 'Unlimited' : value + ' GB';
            premiumDataOptions.scales.y.max = 175;

            const premiumDataData = {
                labels: ['Mint', 'Metro', 'Boost', 'U.S. Cellular', 'AT&T Extra', 'Google Fi', 'Visible+', 'AT&T Prem.', 'Verizon Ult.', 'T-Mobile Beyond'].map(l => wrapLabel(l, 12)),
                datasets: [{
                    label: 'Premium Data (GB)',
                    data: [35, 35, 50, 50, 75, 100, 175, 175, 175, 175],
                    backgroundColor: [brilliantBlues.highlight, brilliantBlues.highlight, brilliantBlues.highlight, brilliantBlues.accent, brilliantBlues.accent, brilliantBlues.accent, brilliantBlues.primary, brilliantBlues.primary, brilliantBlues.primary, brilliantBlues.primary],
                    borderRadius: 5
                }]
            };
            createChart(premiumDataCtx, 'bar', premiumDataData, premiumDataOptions);

            const familyPlanData = {
                 labels: ['Mint', 'Total', 'Google Fi', 'Metro', 'Visible+', 'U.S. Cellular', 'AT&T', 'T-Mobile', 'Verizon'].map(l => wrapLabel(l)),
                datasets: [{
                    label: 'Per-Line Cost (4 Lines)',
                    data: [20, 25, 25, 30, 35, 40, 40.99, 42.50, 55],
                    backgroundColor: brilliantBlues.secondary,
                    borderRadius: 5
                }]
            };
            createChart(familyPlanCtx, 'bar', familyPlanData, { ...chartDefaultOptions });

            const roamingModelData = {
                labels: ['Costly Day Pass (AT&T, Verizon, etc.)', 'Integrated High-Speed Data (T-Mobile, Google Fi)', 'Pay-As-You-Go Credit (Mint, Ultra)'],
                datasets: [{
                    label: 'Roaming Model',
                    data: [4, 2, 4],
                    backgroundColor: [brilliantBlues.primary, brilliantBlues.accent, brilliantBlues.highlight],
                    borderColor: '#fff',
                    borderWidth: 4
                }]
            };
            createChart(roamingModelCtx, 'doughnut', roamingModelData, {
                responsive: true,
                maintainAspectRatio: false,
                 plugins: {
                    legend: {
                        position: 'bottom',
                        labels: {
                            boxWidth: 20,
                            padding: 20,
                             font: {
                               size: 11
                            }
                        }
                    },
                    tooltip: chartDefaultOptions.plugins.tooltip
                 }
            });

            const activationFeeData = {
                labels: ['Visible', 'Mint', 'Google Fi', 'Metro', 'U.S. Cellular', 'AT&T', 'Boost', 'T-Mobile', 'Verizon'].map(l => wrapLabel(l)),
                datasets: [{
                    label: 'Activation Fee',
                    data: [0, 0, 0, 0, 30, 35, 35, 40, 49],
                    backgroundColor: (context) => context.raw === 0 ? brilliantBlues.accent : brilliantBlues.primary,
                    borderRadius: 5
                }]
            };
            createChart(activationFeeCtx, 'bar', activationFeeData, { ...chartDefaultOptions });
        });
    </script>
</body>
</html>
