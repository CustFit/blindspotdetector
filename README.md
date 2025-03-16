<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Customer Blind Spot Detector | CustomersFit</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&display=swap" rel="stylesheet">
    
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

        /* Deeper Dive Section */
        .deeper-dive {
            background-color: var(--secondary-color);
            padding: 30px;
            border-radius: 8px;
            text-align: center;
            margin: 40px 0;
        }

        .deeper-dive h3 {
            color: var(--primary-color);
            margin-bottom: 15px;
        }

        .deeper-dive p {
            margin-bottom: 20px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
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

    <footer>
        <div class="container">
            <div class="deeper-dive" style="background-color: transparent; color: white;">
                <h3 style="color: white;">Ready for a deeper dive?</h3>
                <p>If you've completed this checklist and want to uncover even more profit opportunities in your business, take the next step:</p>
                <a href="https://calendly.com/patricia-rubio/30min-chat" class="btn-primary" target="_blank">Book Your Customer Goldmine Audit</a>
            </div>
            <div class="contact">
                <a href="mailto:hello@customersfit.com">hello@customersfit.com</a>
                <a href="tel:+16692514646">+1 669 251 4646</a>
                <a href="https://www.customersfit.com">www.customersfit.com</a>
            </div>
            <p>© 2025 CustomersFit LLC. All rights reserved.</p>
        </div>
    </footer>
</body>
</html>
