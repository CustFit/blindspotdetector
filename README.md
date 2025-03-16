<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Customer Blind Spot Detector | CustomersFit</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    
    <style>
        /* Base Styles */
        :root {
            --primary-color: #1F497D;
            --secondary-color: #E6EEF7;
            --accent-color: #FF6B35;
            --text-color: #333333;
            --light-gray: #F2F2F2;
            --medium-gray: #CCCCCC;
            --dark-gray: #666666;
            --white: #FFFFFF;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--white);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Typography */
        h1, h2, h3, h4, h5, h6 {
            margin-bottom: 0.5em;
            color: var(--primary-color);
        }

        p {
            margin-bottom: 1em;
        }

        /* Buttons */
        .btn-primary, .btn-secondary {
            display: inline-block;
            padding: 12px 24px;
            border-radius: 4px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
        }

        .btn-primary {
            background-color: var(--accent-color);
            color: var(--white);
        }

        .btn-primary:hover {
            background-color: #e55a2a;
        }

        .btn-secondary {
            background-color: var(--secondary-color);
            color: var(--primary-color);
        }

        .btn-secondary:hover {
            background-color: #d5e3f7;
        }

        /* Header */
        header {
            background-color: var(--white);
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        header .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo h1 {
            font-size: 1.5rem;
            margin: 0;
        }

        /* Hero Section */
        .hero {
            background-color: var(--secondary-color);
            padding: 60px 0;
            text-align: center;
        }

        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
        }

        .hero h2 {
            font-size: 1.5rem;
            font-weight: 500;
            margin-bottom: 20px;
            color: var(--dark-gray);
        }

        .hero p {
            max-width: 800px;
            margin: 0 auto 30px;
        }

        .hero .btn-primary, .hero .btn-secondary {
            margin: 0 10px;
        }

        /* Detector Section */
        .detector {
            padding: 60px 0;
        }

        .zone-container {
            margin-bottom: 30px;
        }

        .zone {
            background-color: var(--white);
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            margin-bottom: 40px; /* Increased spacing between zones */
            overflow: hidden;
        }

        .zone-header {
            background-color: var(--secondary-color);
            padding: 15px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .zone-header h3 {
            margin: 0;
            font-size: 1.2rem;
        }

        .zone-header p {
            margin: 0;
            font-style: italic;
            color: var(--dark-gray);
            font-size: 0.9rem;
        }

        .questions {
            padding: 20px;
            margin-bottom: 20px; /* Added spacing before quick win */
        }

        .question {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            padding-bottom: 15px;
            border-bottom: 1px solid var(--light-gray);
        }

        .question:last-child {
            margin-bottom: 0;
            padding-bottom: 0;
            border-bottom: none;
        }

        .question p {
            flex: 1;
            margin: 0;
            padding-right: 20px;
        }

        .rating {
            display: flex;
            gap: 10px;
        }

        .rating label {
            display: flex;
            flex-direction: column;
            align-items: center;
            cursor: pointer;
        }

        .rating input {
            margin-bottom: 5px;
        }

        .quick-win {
            background-color: var(--light-gray);
            padding: 20px; /* Increased padding */
            font-size: 0.9rem;
            margin-top: 20px; /* Added spacing before quick win */
        }

        .submit-container {
            text-align: center;
            margin-top: 40px; /* Increased spacing */
            margin-bottom: 40px; /* Added spacing after button */
        }

        /* Results Section */
        .results {
            margin-top: 50px;
        }

        .results h2 {
            text-align: center;
            margin-bottom: 30px;
        }

        .results-container {
            display: flex;
            gap: 30px;
            flex-wrap: wrap;
        }

        .results-chart {
            flex: 1;
            min-width: 300px;
        }

        .results-text {
            flex: 1;
            min-width: 300px;
        }

        .interpretation {
            background-color: var(--secondary-color);
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 20px;
        }

        .interpretation h3 {
            margin-top: 0;
        }

        .interpretation ul {
            margin-left: 20px;
            margin-bottom: 15px;
        }

        #recommendation {
            background-color: var(--light-gray);
            padding: 20px;
            border-radius: 8px;
            margin-bottom: 20px;
        }

        .cta {
            background-color: var(--primary-color);
            color: var(--white);
            padding: 20px;
            border-radius: 8px;
            text-align: center;
        }

        .cta h3 {
            color: var(--white);
        }

        .cta p {
            margin-bottom: 20px;
        }

        /* Footer */
        footer {
            background-color: var(--primary-color);
            color: var(--white);
            padding: 30px 0;
        }

        footer .container {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
        }

        footer p {
            margin: 0;
        }

        .contact {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
            justify-content: center;
            margin-bottom: 10px;
        }

        .contact a {
            color: var(--white);
            text-decoration: none;
        }

        .contact a:hover {
            text-decoration: underline;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .zone-header {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .question {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .question p {
                margin-bottom: 10px;
                padding-right: 0;
            }
            
            .rating {
                width: 100%;
                justify-content: space-between;
            }
            
            .contact {
                flex-direction: column;
                gap: 10px;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="logo">
                <h1>CustomersFit</h1>
            </div>
            <nav>
                <a href="https://www.customersfit.com" class="btn-secondary">Visit Main Site</a>
            </nav>
        </div>
    </header>

    <main>
        <section class="hero">
            <div class="container">
                <h1>Customer Blind Spot Detector</h1>
                <h2>Uncover Hidden Profit Opportunities in Your Business</h2>
                <p>Rate your business from 1-5 in each area (1=Complete blind spot, 5=Crystal clear understanding). Areas with lowest scores represent your biggest opportunities for growth.</p>
            </div>
        </section>

        <section id="detector" class="detector">
            <div class="container">
                <form id="blindSpotForm">
                    <div class="zone-container">
                        <div class="zone">
                            <div class="zone-header">
                                <h3>PURCHASE TRIGGERS</h3>
                                <p>What actually prompts buying decisions</p>
                            </div>
                            <div class="questions">
                                <div class="question">
                                    <p>Do you know the specific event or pain point that causes customers to seek your solution?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q1" value="1"> 1</label>
                                        <label><input type="radio" name="q1" value="2"> 2</label>
                                        <label><input type="radio" name="q1" value="3"> 3</label>
                                        <label><input type="radio" name="q1" value="4"> 4</label>
                                        <label><input type="radio" name="q1" value="5"> 5</label>
                                    </div>
                                </div>
                                <div class="question">
                                    <p>Can you identify the emotional triggers that finalize their purchase decision?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q2" value="1"> 1</label>
                                        <label><input type="radio" name="q2" value="2"> 2</label>
                                        <label><input type="radio" name="q2" value="3"> 3</label>
                                        <label><input type="radio" name="q2" value="4"> 4</label>
                                        <label><input type="radio" name="q2" value="5"> 5</label>
                                    </div>
                                </div>
                                <div class="question">
                                    <p>Do you understand the timing factors that influence when customers buy?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q3" value="1"> 1</label>
                                        <label><input type="radio" name="q3" value="2"> 2</label>
                                        <label><input type="radio" name="q3" value="3"> 3</label>
                                        <label><input type="radio" name="q3" value="4"> 4</label>
                                        <label><input type="radio" name="q3" value="5"> 5</label>
                                    </div>
                                </div>
                            </div>
                            
                            <div class="quick-win">
                                <strong>QUICK WIN:</strong> Interview 3 recent customers about what specifically prompted them to buy now rather than later.
                            </div>
                        </div>

                        <div class="zone">
                            <div class="zone-header">
                                <h3>VALUE PERCEPTION</h3>
                                <p>What customers truly value vs. what you think they value</p>
                            </div>
                            <div class="questions">
                                <div class="question">
                                    <p>Can you rank the top 3 features/benefits your customers value most?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q4" value="1"> 1</label>
                                        <label><input type="radio" name="q4" value="2"> 2</label>
                                        <label><input type="radio" name="q4" value="3"> 3</label>
                                        <label><input type="radio" name="q4" value="4"> 4</label>
                                        <label><input type="radio" name="q4" value="5"> 5</label>
                                    </div>
                                </div>
                                <div class="question">
                                    <p>Do you know which aspects of your offering customers would pay more for?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q5" value="1"> 1</label>
                                        <label><input type="radio" name="q5" value="2"> 2</label>
                                        <label><input type="radio" name="q5" value="3"> 3</label>
                                        <label><input type="radio" name="q5" value="4"> 4</label>
                                        <label><input type="radio" name="q5" value="5"> 5</label>
                                    </div>
                                </div>
                                <div class="question">
                                    <p>Have you identified which parts of your service customers don't value?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q6" value="1"> 1</label>
                                        <label><input type="radio" name="q6" value="2"> 2</label>
                                        <label><input type="radio" name="q6" value="3"> 3</label>
                                        <label><input type="radio" name="q6" value="4"> 4</label>
                                        <label><input type="radio" name="q6" value="5"> 5</label>
                                    </div>
                                </div>
                            </div>
                            
                            <div class="quick-win">
                                <strong>QUICK WIN:</strong> Ask customers to allocate 100 points across your features/benefits based on their importance.
                            </div>
                        </div>

                        <div class="zone">
                            <div class="zone-header">
                                <h3>FRICTION POINTS</h3>
                                <p>Hidden obstacles in the customer journey</p>
                            </div>
                            <div class="questions">
                                <div class="question">
                                    <p>Have you mapped all steps in your customer's journey from awareness to purchase?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q7" value="1"> 1</label>
                                        <label><input type="radio" name="q7" value="2"> 2</label>
                                        <label><input type="radio" name="q7" value="3"> 3</label>
                                        <label><input type="radio" name="q7" value="4"> 4</label>
                                        <label><input type="radio" name="q7" value="5"> 5</label>
                                    </div>
                                </div>
                                <div class="question">
                                    <p>Do you know where potential customers most commonly drop out of your sales process?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q8" value="1"> 1</label>
                                        <label><input type="radio" name="q8" value="2"> 2</label>
                                        <label><input type="radio" name="q8" value="3"> 3</label>
                                        <label><input type="radio" name="q8" value="4"> 4</label>
                                        <label><input type="radio" name="q8" value="5"> 5</label>
                                    </div>
                                </div>
                                <div class="question">
                                    <p>Have you identified unstated objections that prevent purchases?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q9" value="1"> 1</label>
                                        <label><input type="radio" name="q9" value="2"> 2</label>
                                        <label><input type="radio" name="q9" value="3"> 3</label>
                                        <label><input type="radio" name="q9" value="4"> 4</label>
                                        <label><input type="radio" name="q9" value="5"> 5</label>
                                    </div>
                                </div>
                            </div>
                            
                            <div class="quick-win">
                                <strong>QUICK WIN:</strong> Track conversion rates between each step of your sales process to identify the biggest drop-offs.
                            </div>
                        </div>

                        <div class="zone">
                            <div class="zone-header">
                                <h3>LOYALTY DRIVERS</h3>
                                <p>Why customers stay beyond the obvious reasons</p>
                            </div>
                            <div class="questions">
                                <div class="question">
                                    <p>Do you know what would make customers switch to a competitor?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q10" value="1"> 1</label>
                                        <label><input type="radio" name="q10" value="2"> 2</label>
                                        <label><input type="radio" name="q10" value="3"> 3</label>
                                        <label><input type="radio" name="q10" value="4"> 4</label>
                                        <label><input type="radio" name="q10" value="5"> 5</label>
                                    </div>
                                </div>
                                <div class="question">
                                    <p>Can you identify the unexpected benefits customers discover after purchase?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q11" value="1"> 1</label>
                                        <label><input type="radio" name="q11" value="2"> 2</label>
                                        <label><input type="radio" name="q11" value="3"> 3</label>
                                        <label><input type="radio" name="q11" value="4"> 4</label>
                                        <label><input type="radio" name="q11" value="5"> 5</label>
                                    </div>
                                </div>
                                <div class="question">
                                    <p>Do you understand which interactions most strengthen customer loyalty?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q12" value="1"> 1</label>
                                        <label><input type="radio" name="q12" value="2"> 2</label>
                                        <label><input type="radio" name="q12" value="3"> 3</label>
                                        <label><input type="radio" name="q12" value="4"> 4</label>
                                        <label><input type="radio" name="q12" value="5"> 5</label>
                                    </div>
                                </div>
                            </div>
                            
                            <div class="quick-win">
                                <strong>QUICK WIN:</strong> Survey long-term customers about what would make them consider alternatives.
                            </div>
                        </div>

                        <div class="zone">
                            <div class="zone-header">
                                <h3>WORD-OF-MOUTH CATALYSTS</h3>
                                <p>What specifically makes customers recommend you</p>
                            </div>
                            <div class="questions">
                                <div class="question">
                                    <p>Do you know exactly what customers tell others about your business?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q13" value="1"> 1</label>
                                        <label><input type="radio" name="q13" value="2"> 2</label>
                                        <label><input type="radio" name="q13" value="3"> 3</label>
                                        <label><input type="radio" name="q13" value="4"> 4</label>
                                        <label><input type="radio" name="q13" value="5"> 5</label>
                                    </div>
                                </div>
                                <div class="question">
                                    <p>Have you identified which customer experiences trigger recommendations?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q14" value="1"> 1</label>
                                        <label><input type="radio" name="q14" value="2"> 2</label>
                                        <label><input type="radio" name="q14" value="3"> 3</label>
                                        <label><input type="radio" name="q14" value="4"> 4</label>
                                        <label><input type="radio" name="q14" value="5"> 5</label>
                                    </div>
                                </div>
                                <div class="question">
                                    <p>Do you understand why some satisfied customers never refer others?</p>
                                    <div class="rating">
                                        <label><input type="radio" name="q15" value="1"> 1</label>
                                        <label><input type="radio" name="q15" value="2"> 2</label>
                                        <label><input type="radio" name="q15" value="3"> 3</label>
                                        <label><input type="radio" name="q15" value="4"> 4</label>
                                        <label><input type="radio" name="q15" value="5"> 5</label>
                                    </div>
                                </div>
                            </div>
                            
                            <div class="quick-win">
                                <strong>QUICK WIN:</strong> Ask recent referrers what specifically prompted them to recommend you.
                            </div>
                        </div>
                    </div>

                    <div class="submit-container">
                        <button type="button" id="calculateButton" class="btn-primary">Calculate My Results</button>
                    </div>
                </form>

                <div id="results" class="results" style="display: none;">
                    <h2>Your Blind Spot Assessment Results</h2>
                    <div class="results-container">
                        <div class="results-chart">
                            <canvas id="resultsChart"></canvas>
                        </div>
                        <div class="results-text">
                            <div id="zoneScores"></div>
                            <div class="interpretation">
                                <h3>Scoring Guide:</h3>
                                <ul>
                                    <li><strong>12-15:</strong> Strong understanding - Maintain and refine</li>
                                    <li><strong>8-11:</strong> Partial visibility - Opportunity for improvement</li>
                                    <li><strong>3-7:</strong> Significant blind spot - Immediate action required</li>
                                </ul>
                                <p>Your lowest-scoring zone represents your biggest opportunity for growth and profit improvement.</p>
                            </div>
                            <div id="recommendation"></div>
                            <div class="cta">
                                <h3>Ready for a complete Customer Goldmine Audit?</h3>
                                <p>Discover all your hidden profit opportunities with our comprehensive audit.</p>
                                <a href="https://www.customersfit.com" class="btn-primary">Learn More</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <div class="contact">
                <a href="mailto:hello@customersfit.com">hello@customersfit.com</a>
                <a href="tel:+16692514646">+1 669 251 4646</a>
                <a href="https://www.customersfit.com">www.customersfit.com</a>
            </div>
            <p>© 2025 CustomersFit LLC. All rights reserved.</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const form = document.getElementById('blindSpotForm');
            const calculateButton = document.getElementById('calculateButton');
            const results = document.getElementById('results');
            const zoneScores = document.getElementById('zoneScores');
            const recommendation = document.getElementById('recommendation');
            let chart;

            calculateButton.addEventListener('click', function() {
                // Calculate scores for each zone
                const scores = {
                    'PURCHASE TRIGGERS': calculateZoneScore(1, 3),
                    'VALUE PERCEPTION': calculateZoneScore(4, 6),
                    'FRICTION POINTS': calculateZoneScore(7, 9),
                    'LOYALTY DRIVERS': calculateZoneScore(10, 12),
                    'WORD-OF-MOUTH CATALYSTS': calculateZoneScore(13, 15)
                };
                
                // Display results
                displayResults(scores);
                
                // Show results section
                results.style.display = 'block';
                
                // Scroll to results
                results.scrollIntoView({ behavior: 'smooth' });
            });

            function calculateZoneScore(startQ, endQ) {
                let score = 0;
                let answeredQuestions = 0;
                
                for (let i = startQ; i <= endQ; i++) {
                    const radios = document.getElementsByName('q' + i);
                    for (let j = 0; j < radios.length; j++) {
                        if (radios[j].checked) {
                            score += parseInt(radios[j].value);
                            answeredQuestions++;
                            break;
                        }
                    }
                }
                
                // If all questions in zone are answered, return score
                if (answeredQuestions === (endQ - startQ + 1)) {
                    return score;
                }
                
                // If some questions are unanswered, return proportional score
                // If no questions answered, return 0
                return answeredQuestions > 0 ? Math.round(score * 3 / answeredQuestions) : 0;
            }

            function displayResults(scores) {
                // Clear previous results
                zoneScores.innerHTML = '';
                
                // Create HTML for zone scores
                let html = '<h3>Your Zone Scores:</h3><ul>';
                
                // Find lowest score and its zone
                let lowestScore = 15;
                let lowestZone = '';
                
                Object.entries(scores).forEach(([zone, score]) => {
                    let status;
                    if (score >= 12) {
                        status = '<span style="color: green;">Strong understanding</span>';
                    } else if (score >= 8) {
                        status = '<span style="color: orange;">Partial visibility</span>';
                    } else {
                        status = '<span style="color: red;">Significant blind spot</span>';
                    }
                    
                    html += `<li><strong>${zone}:</strong> ${score}/15 - ${status}</li>`;
                    
                    if (score < lowestScore) {
                        lowestScore = score;
                        lowestZone = zone;
                    }
                });
                
                html += '</ul>';
                zoneScores.innerHTML = html;
                
                // Create recommendation based on lowest score
                let recommendationText = `<h3>Your Biggest Opportunity:</h3>
                    <p>Based on your assessment, your biggest opportunity for growth is in the <strong>${lowestZone}</strong> zone with a score of ${lowestScore}/15.</p>`;
                
                // Add specific recommendation based on zone
                switch(lowestZone) {
                    case 'PURCHASE TRIGGERS':
                        recommendationText += `<p>Focus on understanding what specifically prompts customers to seek your solution. Interview recent customers about their buying journey and the specific events that triggered their search.</p>`;
                        break;
                    case 'VALUE PERCEPTION':
                        recommendationText += `<p>Work on identifying what your customers truly value most about your offering. Consider conducting a value allocation exercise where customers distribute points across your features/benefits.</p>`;
                        break;
                    case 'FRICTION POINTS':
                        recommendationText += `<p>Map your complete customer journey and identify where potential customers are dropping out. Track conversion rates between each step of your sales process.</p>`;
                        break;
                    case 'LOYALTY DRIVERS':
                        recommendationText += `<p>Investigate what keeps your customers loyal beyond the obvious reasons. Survey long-term customers about what would make them consider alternatives.</p>`;
                        break;
                    case 'WORD-OF-MOUTH CATALYSTS':
                        recommendationText += `<p>Discover what specifically makes customers recommend you to others. Ask recent referrers what prompted them to recommend your business.</p>`;
                        break;
                }
                
                recommendation.innerHTML = recommendationText;
                
                // Create or update chart
                createChart(scores);
            }

            function createChart(scores) {
                const ctx = document.getElementById('resultsChart').getContext('2d');
                
                // Destroy previous chart if it exists
                if (chart) {
                    chart.destroy();
                }
                
                // Create new chart
                chart = new Chart(ctx, {
                    type: 'radar',
                    data: {
                        labels: Object.keys(scores),
                        datasets: [{
                            label: 'Your Score',
                            data: Object.values(scores),
                            backgroundColor: 'rgba(255, 107, 53, 0.2)',
                            borderColor: 'rgba(255, 107, 53, 1)',
                            borderWidth: 2,
                            pointBackgroundColor: 'rgba(255, 107, 53, 1)'
                        }]
