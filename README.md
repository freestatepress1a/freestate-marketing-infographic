<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FreeState Marketing: Interactive Brand Hub</title>
    <!-- Chosen Palette: Professional & Stylish -->
    <!-- Application Structure Plan: The application is designed as an interactive brand hub, using a clean, section-based layout with top navigation. The structure includes a prominent hero section for the vision, a detailed mission breakdown, and an interactive card grid for the core values. This structure was chosen to allow users (partners, employees, clients) to explore the brand's identity in a non-linear, self-directed way, focusing on clarity and engagement over a linear narrative. The interactive cards for values, in particular, encourage deeper exploration of each principle. -->
    <!-- Visualization & Content Choices: 
        - Vision/Mission: Presented as clear, styled text blocks to serve an "Inform" goal, establishing the brand's core purpose immediately.
        - Core Values: Presented as interactive cards. Goal: "Organize" and "Inform". Method: HTML/CSS/JS. Interaction: On-click reveal of detailed descriptions. Justification: This method encourages user engagement and allows for a clean, uncluttered initial view while providing depth on demand.
        - Strategic Focus Chart: A horizontal bar chart to "Compare" key strategic pillars. Method: Chart.js. Interaction: Tooltips on hover. Justification: A bar chart provides a clear, quantitative-style comparison of the company's main efforts, effectively summarizing the mission's focus areas.
    -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #fdfaf6;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            height: 400px;
            max-height: 500px;
        }
        .value-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .value-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
        .value-card .description {
            display: none;
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-in-out;
        }
        .value-card.active .description {
            display: block;
            max-height: 500px;
        }
    </style>
</head>
<body class="text-gray-800">

    <nav class="bg-white/80 backdrop-blur-md sticky top-0 z-50 shadow-sm">
        <div class="container mx-auto px-6 py-3 flex justify-between items-center">
            <h1 class="text-xl font-bold" style="color: #264653;">FreeState Marketing</h1>
            <div class="hidden md:flex space-x-8">
                <a href="#vision" class="hover:text-[#2A9D8F]">Our Vision</a>
                <a href="#mission" class="hover:text-[#2A9D8F]">Our Mission</a>
                <a href="#values" class="hover:text-[#2A9D8F]">Core Values</a>
                <a href="#focus" class="hover:text-[#2A9D8F]">Strategic Focus</a>
            </div>
        </div>
    </nav>

    <main class="container mx-auto px-6 py-12">

        <section id="vision" class="text-center my-16">
            <h2 class="text-sm font-bold uppercase tracking-widest" style="color: #E76F51;">Our Vision</h2>
            <p class="mt-4 text-3xl md:text-5xl font-extrabold max-w-4xl mx-auto" style="color: #264653;">
                To build a marketing powerhouse that honors American values, empowers generational wealth, and enriches the lives of Americans.
            </p>
        </section>

        <section id="mission" class="my-24 bg-white rounded-lg shadow-lg p-8 md:p-12">
            <h2 class="text-3xl font-bold text-center mb-4" style="color: #264653;">Our Mission</h2>
            <p class="text-lg text-center max-w-5xl mx-auto text-gray-600">
                FreeState Marketing is dedicated to serving as an innovative, resourceful, and resilient force in the digital marketing landscape. We specialize in affiliate, brand, and digital marketing, focusing exclusively on American-made products and services. Through strategic, thoughtful, and fluid actions, we aim to build robust platforms for our family of brands—including FreeState Survival, FreeState Wellness, FreeState Apothecary, and FreeState Press—and for our partners. A core part of our mission is to empower small businesses, providing them with the tools and visibility needed to succeed against large corporate interests. Our goal is to create a foundation for long-term prosperity, passing on not only a thriving business but a legacy of unwavering commitment to our American heritage.
            </p>
        </section>

        <section id="values" class="my-24">
            <h2 class="text-3xl font-bold text-center mb-10" style="color: #264653;">Our Foundational Core Values</h2>
            <div id="values-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                
                <div class="value-card bg-white rounded-lg shadow-md p-6 cursor-pointer" data-value="1">
                    <h3 class="text-xl font-bold" style="color: #2A9D8F;">Resourcefulness & Resilience</h3>
                    <div class="description mt-4 text-gray-600">We believe in the power of ingenuity and perseverance. Just as life is asymmetrical, our approach must be elastic and adaptive. We find solutions where others see dead ends, and we build from the ground up, turning challenges into opportunities for growth.</div>
                </div>

                <div class="value-card bg-white rounded-lg shadow-md p-6 cursor-pointer" data-value="2">
                    <h3 class="text-xl font-bold" style="color: #2A9D8F;">Integrity & Conviction</h3>
                    <div class="description mt-4 text-gray-600">Our actions are a reflection of our deeply held beliefs. We operate with honesty and transparency, guided by Constitutional and Christian principles. Our commitment to promoting American exceptionalism and supporting our fellow countrymen is at the heart of everything we do.</div>
                </div>

                <div class="value-card bg-white rounded-lg shadow-md p-6 cursor-pointer" data-value="3">
                    <h3 class="text-xl font-bold" style="color: #2A9D8F;">Legacy & Generational Stewardship</h3>
                    <div class="description mt-4 text-gray-600">We are not just building a business for today; we are laying a foundation for future generations. Every decision is made with an eye toward long-term sustainability, ensuring that we create a heritage of both financial and spiritual abundance.</div>
                </div>

                <div class="value-card bg-white rounded-lg shadow-md p-6 cursor-pointer" data-value="4">
                    <h3 class="text-xl font-bold" style="color: #2A9D8F;">Freedom & Expression</h3>
                    <div class="description mt-4 text-gray-600">We are protected by and uphold the First Amendment of the United States. We believe in the right to express our values freely and responsibly, using our platforms to champion causes and products that reflect our commitment to liberty and a thriving America.</div>
                </div>

                <div class="value-card bg-white rounded-lg shadow-md p-6 cursor-pointer" data-value="5">
                    <h3 class="text-xl font-bold" style="color: #2A9D8F;">Fluidity & Adaptability</h3>
                    <div class="description mt-4 text-gray-600">The digital landscape is always changing. We embrace this dynamic environment by remaining fluid and flexible, ready to adjust our strategies to meet new challenges and seize emerging opportunities. Our asymmetrical approach ensures we can pivot quickly and effectively.</div>
                </div>
                
                <div class="value-card bg-white rounded-lg shadow-md p-6 cursor-pointer" data-value="6">
                    <h3 class="text-xl font-bold" style="color: #2A9D8F;">Championing the Underdog</h3>
                    <div class="description mt-4 text-gray-600">We believe the backbone of our economy is the small business owner. We are committed to leveling the playing field, providing our partners with the strategic advantage to not just survive but thrive in a market dominated by corporate interests.</div>
                </div>
                
                 <div class="value-card bg-white rounded-lg shadow-md p-6 cursor-pointer md:col-span-2 lg:col-span-1" data-value="7">
                    <h3 class="text-xl font-bold" style="color: #2A9D8F;">Shared Prosperity & Team Stewardship</h3>
                    <div class="description mt-4 text-gray-600">We believe that true success is a collective achievement. We are committed to a model of shared prosperity, ensuring that every individual who contributes to our mission has the opportunity to succeed and share in the profits. We are not just building a company, but a legacy where the efforts of one benefit all, and where we are all stewards of the foundation we build together for future generations.</div>
                </div>

            </div>
        </section>

        <section id="focus" class="my-24 bg-white rounded-lg shadow-lg p-8 md:p-12">
             <h2 class="text-3xl font-bold text-center mb-2" style="color: #264653;">Our Strategic Focus</h2>
             <p class="text-lg text-center max-w-3xl mx-auto text-gray-600 mb-10">Our mission is concentrated on three key pillars that drive every decision we make.</p>
             <div class="chart-container">
                <canvas id="strategicFocusChart"></canvas>
            </div>
        </section>

    </main>

    <footer style="background-color: #264653;" class="text-white text-center py-12">
        <h2 class="text-3xl font-bold">A Legacy in the Making</h2>
        <p class="mt-4 max-w-2xl mx-auto">
            This is more than a business; it's a testament to shared values and a blueprint for our collective future.
        </p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const valueCards = document.querySelectorAll('.value-card');
            valueCards.forEach(card => {
                card.addEventListener('click', () => {
                    card.classList.toggle('active');
                });
            });

            const palette = {
                darkBlue: '#264653',
                teal: '#2A9D8F',
                yellow: '#E9C46A',
                sandy: '#F4A261',
                orange: '#E76F51'
            };

            const tooltipTitleCallback = {
                plugins: {
                    tooltip: {
                        callbacks: {
                            title: function(tooltipItems) {
                                const item = tooltipItems[0];
                                let label = item.chart.data.labels[item.dataIndex];
                                if (Array.isArray(label)) {
                                    return label.join(' ');
                                } else {
                                    return label;
                                }
                            }
                        }
                    }
                }
            };
            
            new Chart(document.getElementById('strategicFocusChart'), {
                type: 'bar',
                data: {
                    labels: ['Empowering Small Business', 'Championing American-Made', 'Building Generational Wealth'],
                    datasets: [{
                        label: 'Focus Level',
                        data: [100, 95, 90],
                        backgroundColor: [palette.teal, palette.yellow, palette.sandy],
                        borderColor: [palette.darkBlue],
                        borderWidth: 1
                    }]
                },
                options: {
                    indexAxis: 'y',
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        ...tooltipTitleCallback.plugins,
                        legend: {
                            display: false
                        },
                        title: {
                            display: false
                        }
                    },
                    scales: {
                        x: {
                            beginAtZero: true,
                             grid: {
                                display: false,
                                drawBorder: false
                            },
                            ticks: {
                                display: false
                            }
                        },
                        y: {
                            grid: {
                                display: false,
                                drawBorder: false
                            },
                            ticks: {
                                color: palette.darkBlue,
                                font: {
                                    size: 14,
                                    weight: 'bold'
                                }
                            }
                        }
                    }
                }
            });
        });
    </script>
</body>
</html>
