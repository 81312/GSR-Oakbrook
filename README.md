# GSR-Oakbrook
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>U.S. Cellular Plan Infographic</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700;800&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Energetic & Playful (#FF6B6B, #FFD166, #06D6A0, #118AB2, #073B4C) -->
    <!-- Application Structure Plan: The infographic follows a top-down narrative structure designed for easy scrolling and comprehension. It begins with a high-level overview (The Two Flavors of Cell Service), moves to the primary point of comparison (Monthly Cost), dives into a key differentiator (International Travel), details specific features (Data & Perks), clarifies underlying infrastructure (Network Coverage), and concludes with actionable recommendations (Who Is It Best For?). This linear story-telling approach guides the user from general knowledge to specific insights, making the complex data digestible. -->
    <!-- Visualization & Content Choices: 
        - Monthly Cost -> Goal: Compare -> Viz: Bar Chart (Chart.js) -> Justification: Provides a clear, immediate comparison of the primary cost factor for users.
        - International Cost -> Goal: Inform -> Viz: Donut Chart (Chart.js) -> Justification: Emphasizes the stark difference and high value of Google Fi's offer ($0) versus a tangible competitor cost, making the point impactful.
        - Data Caps -> Goal: Compare -> Viz: Grouped Bar Chart (Chart.js) -> Justification: Allows for a nuanced comparison of two key data metrics (premium data vs. hotspot data) side-by-side for each carrier.
        - Perks -> Goal: Organize -> Viz: Styled HTML Grid with Unicode -> Justification: Presents qualitative, non-numeric data in a visually scannable format that is cleaner than a table.
        - Network Relationship -> Goal: Organize -> Viz: HTML/CSS Flow Diagram -> Justification: Illustrates the MVNO-carrier relationship simply and visually without requiring complex libraries or graphics.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #F8FAFC;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            height: 350px;
            max-height: 50vh;
        }
        .donut-chart-container {
            position: relative;
            width: 100%;
            max-width: 350px;
            margin-left: auto;
            margin-right: auto;
            height: 350px;
        }
        .big-number {
            font-size: 5rem;
            font-weight: 800;
            line-height: 1;
            color: #118AB2;
        }
        .card {
            background-color: white;
            border-radius: 0.75rem;
            padding: 1.5rem;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
            margin-bottom: 2rem;
        }
        @media (min-width: 768px) {
            .card {
                padding: 2rem;
            }
        }
    </style>
</head>
<body class="text-slate-700">

    <div class="container mx-auto px-4 py-12 max-w-5xl">

        <header class="text-center mb-16">
            <h1 class="text-4xl md:text-5xl font-extrabold text-[#073B4C] mb-4">The U.S. Cellular Showdown</h1>
            <p class="text-lg text-slate-600">A visual guide to comparing the major carriers and seeing where Google Fi fits in.</p>
        </header>

        <section class="card text-center">
            <h2 class="text-3xl font-bold text-[#073B4C] mb-4">The Two Flavors of Cell Service</h2>
            <p class="max-w-3xl mx-auto mb-6">The U.S. market is dominated by two types of providers. Understanding the difference is the first step to choosing the right plan for you.</p>
            <div class="grid md:grid-cols-2 gap-8 text-left">
                <div class="bg-slate-100 p-6 rounded-lg">
                    <h3 class="text-xl font-bold text-[#118AB2] mb-2">The "Big Three" Networks</h3>
                    <p class="text-slate-600">Verizon, AT&T, and T-Mobile own and operate the physical cell towers. They offer premium plans, often with perks, but usually at the highest price.</p>
                </div>
                <div class="bg-slate-100 p-6 rounded-lg">
                    <h3 class="text-xl font-bold text-[#06D6A0] mb-2">The MVNOs</h3>
                    <p class="text-slate-600">Mobile Virtual Network Operators, like Google Fi, Mint Mobile, and Visible, lease network access from the "Big Three." They pass the savings on to you, offering flexible, lower-cost plans.</p>
                </div>
            </div>
        </section>

        <section class="card">
            <h2 class="text-3xl font-bold text-center text-[#073B4C] mb-2">The Main Event: Monthly Cost</h2>
            <p class="text-center max-w-3xl mx-auto mb-8">This is the bottom line for most people. Here’s how the top-tier unlimited plans from each carrier stack up for a single line.</p>
            <div class="chart-container">
                <canvas id="priceChart"></canvas>
            </div>
        </section>

        <section class="card">
            <h2 class="text-3xl font-bold text-center text-[#073B4C] mb-4">The Google Fi Difference: International Travel</h2>
            <p class="text-center max-w-3xl mx-auto mb-8">For frequent flyers, this is a game-changer. Google Fi's Unlimited Plus plan includes free data abroad, while others charge hefty daily fees.</p>
            <div class="grid md:grid-cols-2 gap-8 items-center">
                <div class="text-center">
                    <p class="text-lg text-slate-600">Estimated cost for a 7-day international trip:</p>
                    <div class="big-number my-4 text-[#FF6B6B]">$70</div>
                    <p class="font-bold text-xl text-slate-800">Other Major Carriers</p>
                    <p class="text-slate-500">($10/day TravelPass)</p>
                </div>
                <div class="donut-chart-container">
                    <canvas id="internationalCostChart"></canvas>
                </div>
            </div>
        </section>

        <section class="card">
            <h2 class="text-3xl font-bold text-center text-[#073B4C] mb-2">Deeper Dive: Data Caps & Perks</h2>
            <p class="text-center max-w-3xl mx-auto mb-8">"Unlimited" isn't always truly unlimited. We compare premium data (before potential slowdowns) and high-speed hotspot data. Plus, see what entertainment perks are included.</p>
            <div class="grid md:grid-cols-2 gap-12">
                <div>
                    <h3 class="text-xl font-bold text-center text-[#118AB2] mb-4">Data Allowances (in GB)</h3>
                    <div class="chart-container" style="height: 400px;">
                        <canvas id="dataChart"></canvas>
                    </div>
                </div>
                <div>
                    <h3 class="text-xl font-bold text-center text-[#118AB2] mb-4">Streaming & Service Perks</h3>
                    <div class="space-y-4">
                        <div class="p-4 rounded-lg bg-slate-50 border border-slate-200">
                            <p class="font-bold text-lg text-slate-800">Google Fi</p>
                            <p>✓ YouTube Premium (6mo) <br> ✓ Google One Storage (100GB)</p>
                        </div>
                        <div class="p-4 rounded-lg bg-slate-50 border border-slate-200">
                            <p class="font-bold text-lg text-slate-800">T-Mobile</p>
                            <p>✓ Netflix <br> ✓ Apple TV+</p>
                        </div>
                        <div class="p-4 rounded-lg bg-slate-50 border border-slate-200">
                            <p class="font-bold text-lg text-slate-800">Verizon</p>
                            <p>✓ Optional Add-ons for Disney+, Hulu, etc. ($10/mo each)</p>
                        </div>
                        <div class="p-4 rounded-lg bg-slate-50 border border-slate-200">
                            <p class="font-bold text-lg text-slate-800">AT&T</p>
                            <p>✗ Few to no perks typically included in standard plans.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="card">
            <h2 class="text-3xl font-bold text-center text-[#073B4C] mb-4">Behind the Scenes: Network Coverage</h2>
            <p class="text-center max-w-3xl mx-auto mb-8">Google Fi doesn't own towers; it uses T-Mobile's powerful 5G network. Here’s a simplified look at the landscape and each major network's strength.</p>
            <div class="flex flex-col items-center space-y-4">
                <div class="p-4 bg-[#FFD166] text-[#073B4C] rounded-lg font-bold shadow-md">Google Fi</div>
                <div class="text-2xl font-bold text-slate-400">↓</div>
                <div class="p-4 bg-[#118AB2] text-white rounded-lg font-bold shadow-md">T-Mobile Network</div>
                <div class="mt-8 grid md:grid-cols-3 gap-4 text-center w-full pt-4 border-t border-slate-200">
                    <div>
                        <h4 class="font-bold text-lg text-slate-800">T-Mobile</h4>
                        <p class="text-slate-600">🏆 Best 5G Speed & Reach</p>
                    </div>
                    <div>
                        <h4 class="font-bold text-lg text-slate-800">Verizon</h4>
                        <p class="text-slate-600">🏕️ Best Rural Coverage</p>
                    </div>
                    <div>
                        <h4 class="font-bold text-lg text-slate-800">AT&T</h4>
                        <p class="text-slate-600"> balanced performance</p>
                    </div>
                </div>
            </div>
        </section>
        
        <section>
            <h2 class="text-3xl font-bold text-center text-[#073B4C] mb-8">So... Which Plan Is Best For You?</h2>
            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div class="p-6 rounded-lg bg-white shadow-md border-t-4 border-[#06D6A0]">
                    <h3 class="text-xl font-bold text-[#073B4C] mb-3">Choose Google Fi if...</h3>
                    <ul class="list-none space-y-2 text-slate-600">
                        <li class="flex items-start"><span class="mr-2 text-[#06D6A0]">✈️</span> You're a frequent international traveler.</li>
                        <li class="flex items-start"><span class="mr-2 text-[#06D6A0]">💰</span> You use very little data and want to save money.</li>
                        <li class="flex items-start"><span class="mr-2 text-[#06D6A0]"> simplicity.</li>
                    </ul>
                </div>
                <div class="p-6 rounded-lg bg-white shadow-md border-t-4 border-[#118AB2]">
                    <h3 class="text-xl font-bold text-[#073B4C] mb-3">Choose T-Mobile if...</h3>
                    <ul class="list-none space-y-2 text-slate-600">
                        <li class="flex items-start"><span class="mr-2 text-[#118AB2]">🚀</span> You want the fastest 5G experience.</li>
                        <li class="flex items-start"><span class="mr-2 text-[#118AB2]">🎁</span> You want the most perks, like Netflix, included.</li>
                        <li class="flex items-start"><span class="mr-2 text-[#118AB2]">👨‍👩‍👧‍👦</span> You have a family and need great multi-line value.</li>
                    </ul>
                </div>
                <div class="p-6 rounded-lg bg-white shadow-md border-t-4 border-[#FF6B6B] md:col-span-2 lg:col-span-1">
                    <h3 class="text-xl font-bold text-[#073B4C] mb-3">Choose Verizon or AT&T if...</h3>
                    <ul class="list-none space-y-2 text-slate-600">
                        <li class="flex items-start"><span class="mr-2 text-[#FF6B6B]">🏞️</span> You need the absolute most reliable coverage in rural areas (Verizon).</li>
                        <li class="flex items-start"><span class="mr-2 text-[#FF6B6B]"> Latin America (AT&T).</li>
                    </ul>
                </div>
            </div>
        </section>

    </div>

    <script>
        const chartColors = {
            red: '#FF6B6B',
            yellow: '#FFD166',
            green: '#06D6A0',
            blue: '#118AB2',
            darkBlue: '#073B4C',
            slate: '#64748B'
        };

        const chartTooltipConfig = {
            plugins: {
                tooltip: {
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
            }
        };
        
        const wrapLabel = (label) => {
            const maxLen = 16;
            if (label.length > maxLen) {
                const words = label.split(' ');
                const lines = [];
                let currentLine = '';
                for (const word of words) {
                    if ((currentLine + word).length > maxLen) {
                        lines.push(currentLine.trim());
                        currentLine = '';
                    }
                    currentLine += word + ' ';
                }
                lines.push(currentLine.trim());
                return lines.filter(line => line);
            }
            return label;
        };
        
        new Chart(document.getElementById('priceChart'), {
            type: 'bar',
            data: {
                labels: ['Google Fi', 'AT&T', 'T-Mobile', 'Verizon'],
                datasets: [{
                    label: 'Monthly Price ($)',
                    data: [65, 86, 90, 90],
                    backgroundColor: [chartColors.green, chartColors.slate, chartColors.red, chartColors.blue],
                }]
            },
            options: { ...chartTooltipConfig,
                responsive: true,
                maintainAspectRatio: false,
                plugins: { ...chartTooltipConfig.plugins,
                    legend: { display: false }
                },
                scales: {
                    y: {
                        beginAtZero: true,
                        title: { display: true, text: 'Price per month ($)' }
                    }
                }
            }
        });

        new Chart(document.getElementById('internationalCostChart'), {
            type: 'doughnut',
            data: {
                labels: ['Google Fi', 'Other Carriers (7-day trip est.)'],
                datasets: [{
                    label: 'Cost',
                    data: [0, 70],
                    backgroundColor: [chartColors.green, chartColors.red],
                    hoverOffset: 4
                }]
            },
            options: { ...chartTooltipConfig,
                responsive: true,
                maintainAspectRatio: false,
                plugins: { ...chartTooltipConfig.plugins,
                    legend: { position: 'bottom' }
                },
                cutout: '60%'
            }
        });

        new Chart(document.getElementById('dataChart'), {
            type: 'bar',
            data: {
                labels: ['Google Fi', 'T-Mobile', 'AT&T', 'Verizon'],
                datasets: [{
                    label: 'Premium Data (GB)',
                    data: [50, 200, 200, 200],
                    backgroundColor: chartColors.blue,
                }, {
                    label: 'Hotspot Data (GB)',
                    data: [50, 50, 60, 60],
                    backgroundColor: chartColors.yellow,
                }]
            },
            options: { ...chartTooltipConfig,
                responsive: true,
                maintainAspectRatio: false,
                plugins: { ...chartTooltipConfig.plugins,
                    legend: { position: 'bottom' }
                },
                scales: {
                    y: {
                        beginAtZero: true,
                        title: { display: true, text: 'Gigabytes (GB)' },
                        ticks: {
                             callback: function(value, index, ticks) {
                                return value === 200 ? 'Unlimited' : value;
                            }
                        }
                    }
                }
            }
        });

    </script>

</body>
</html>
