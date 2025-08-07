<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Performance Testing Engagement Form</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 24px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #ff6b6b 0%, #ee5a24 100%);
            color: white;
            padding: 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: pulse 4s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.1); opacity: 0.8; }
        }

        .header h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .header p {
            font-size: 1.2em;
            opacity: 0.9;
        }

        .content {
            padding: 40px;
        }

        .section {
            margin-bottom: 40px;
            background: #f8f9fa;
            border-radius: 16px;
            padding: 30px;
            border-left: 5px solid #667eea;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .section:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .section-title {
            font-size: 1.8em;
            color: #333;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .section-title::before {
            content: attr(data-icon);
            font-size: 1.2em;
            background: linear-gradient(135deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 25px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
        }

        .form-group label {
            font-weight: 600;
            color: #555;
            margin-bottom: 8px;
            font-size: 0.95em;
        }

        .form-group input, .form-group select, .form-group textarea {
            padding: 12px 16px;
            border: 2px solid #e9ecef;
            border-radius: 8px;
            font-size: 1em;
            transition: border-color 0.3s ease, box-shadow 0.3s ease;
        }

        .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
            outline: none;
            border-color: #667eea;
            box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
        }

        .checkbox-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
            margin: 20px 0;
        }

        .checkbox-item {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 15px;
            background: white;
            border: 2px solid #e9ecef;
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .checkbox-item:hover {
            border-color: #667eea;
            transform: translateY(-1px);
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }

        .checkbox-item input[type="checkbox"] {
            width: 20px;
            height: 20px;
            accent-color: #667eea;
        }

        .checkbox-item label {
            font-weight: 500;
            cursor: pointer;
            flex: 1;
        }

        .impact-table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
        }

        .impact-table th {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 16px;
            text-align: left;
            font-weight: 600;
        }

        .impact-table td {
            padding: 16px;
            border-bottom: 1px solid #e9ecef;
        }

        .impact-table tr:nth-child(even) {
            background: #f8f9fa;
        }

        .impact-table tr:hover {
            background: #e3f2fd;
        }

        .star-rating {
            display: flex;
            gap: 4px;
        }

        .star-rating input {
            display: none;
        }

        .star-rating label {
            font-size: 1.5em;
            color: #ddd;
            cursor: pointer;
            transition: color 0.2s ease;
        }

        .star-rating label:hover,
        .star-rating label:hover ~ label,
        .star-rating input:checked ~ label {
            color: #ffc107;
        }

        .highlight-box {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 25px;
            border-radius: 16px;
            margin: 25px 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .highlight-box::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: rotate 8s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .highlight-box h3 {
            font-size: 1.5em;
            margin-bottom: 10px;
            position: relative;
            z-index: 1;
        }

        .highlight-box p {
            font-size: 1.1em;
            opacity: 0.9;
            position: relative;
            z-index: 1;
        }

        .timeline-item {
            display: flex;
            align-items: center;
            gap: 20px;
            margin: 20px 0;
            padding: 20px;
            background: white;
            border-radius: 12px;
            border-left: 4px solid #667eea;
        }

        .timeline-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 1.2em;
        }

        .timeline-content {
            flex: 1;
        }

        .timeline-content h4 {
            color: #333;
            margin-bottom: 5px;
        }

        .timeline-content p {
            color: #666;
            font-size: 0.9em;
        }

        .tips-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .tip-card {
            background: white;
            padding: 25px;
            border-radius: 16px;
            border-top: 4px solid #667eea;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .tip-card:hover {
            transform: translateY(-4px);
        }

        .tip-card h4 {
            color: #333;
            margin-bottom: 15px;
            font-size: 1.2em;
        }

        .tip-card ul {
            color: #666;
            line-height: 1.6;
        }

        .tip-card li {
            margin-bottom: 8px;
        }

        .progress-bar {
            width: 100%;
            height: 6px;
            background: #e9ecef;
            border-radius: 3px;
            overflow: hidden;
            margin: 20px 0;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #667eea, #764ba2);
            width: 0%;
            transition: width 0.3s ease;
        }

        .contact-card {
            background: linear-gradient(135deg, #00c9ff, #92fe9d);
            color: white;
            padding: 30px;
            border-radius: 16px;
            text-align: center;
            margin: 30px 0;
        }

        .contact-card h3 {
            font-size: 1.8em;
            margin-bottom: 15px;
        }

        .contact-card p {
            font-size: 1.1em;
            opacity: 0.9;
        }

        .submit-section {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            padding: 40px;
            border-radius: 16px;
            text-align: center;
            margin-top: 40px;
        }

        .submit-btn {
            background: white;
            color: #667eea;
            padding: 15px 40px;
            border: none;
            border-radius: 25px;
            font-size: 1.2em;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 20px;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.2);
        }

        @media (max-width: 768px) {
            .form-grid {
                grid-template-columns: 1fr;
            }
            
            .checkbox-grid {
                grid-template-columns: 1fr;
            }
            
            .header h1 {
                font-size: 2em;
            }
            
            .content {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🚀 Performance Testing Engagement</h1>
            <p>Let's Build Something Amazing Together</p>
        </div>

        <div class="content">
            <div class="highlight-box">
                <h3>🎯 Our Mission</h3>
                <p>Transform your business vision into a lightning-fast, rock-solid user experience that delights customers and drives growth</p>
            </div>

            <div class="section">
                <h2 class="section-title" data-icon="📋">Project Overview</h2>
                <div class="form-grid">
                    <div class="form-group">
                        <label for="project-name">Project Name *</label>
                        <input type="text" id="project-name" name="project-name" required>
                    </div>
                    <div class="form-group">
                        <label for="project-owner">Project Owner/Sponsor *</label>
                        <input type="text" id="project-owner" name="project-owner" required>
                    </div>
                    <div class="form-group">
                        <label for="primary-contact">Primary Contact *</label>
                        <input type="text" id="primary-contact" name="primary-contact" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Email *</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="start-date">Requested Start Date</label>
                        <input type="date" id="start-date" name="start-date">
                    </div>
                    <div class="form-group">
                        <label for="launch-date">Expected Launch Date</label>
                        <input type="date" id="launch-date" name="launch-date">
                    </div>
                </div>
                <div class="form-group">
                    <label for="project-description">What does this system do? (In simple terms) *</label>
                    <textarea id="project-description" name="project-description" rows="4" placeholder="Example: This is a customer portal where clients can view their account balance, make payments, and download statements." required></textarea>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title" data-icon="👥">Who Uses This System?</h2>
                <div class="checkbox-grid">
                    <div class="checkbox-item">
                        <input type="checkbox" id="internal-users" name="user-types" value="internal">
                        <label for="internal-users">Internal Employees</label>
                        <input type="number" placeholder="How many?" style="width: 100px;">
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" id="external-customers" name="user-types" value="external">
                        <label for="external-customers">External Customers</label>
                        <input type="number" placeholder="How many?" style="width: 100px;">
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" id="partners" name="user-types" value="partners">
                        <label for="partners">Partners/Vendors</label>
                        <input type="number" placeholder="How many?" style="width: 100px;">
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" id="public-users" name="user-types" value="public">
                        <label for="public-users">Public Users</label>
                        <input type="number" placeholder="Expected?" style="width: 100px;">
                    </div>
                </div>

                <h3>⏰ When Do People Use It Most?</h3>
                <div class="checkbox-grid">
                    <div class="checkbox-item">
                        <input type="checkbox" id="business-hours" name="usage-times" value="business-hours">
                        <label for="business-hours">Business Hours (9 AM - 5 PM)</label>
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" id="extended-hours" name="usage-times" value="extended-hours">
                        <label for="extended-hours">Extended Hours (7 AM - 9 PM)</label>
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" id="twentyfour-seven" name="usage-times" value="24-7">
                        <label for="twentyfour-seven">24/7 Availability Required</label>
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" id="peak-times" name="usage-times" value="peak-times">
                        <label for="peak-times">Specific Peak Times</label>
                        <input type="text" placeholder="When?" style="width: 120px;">
                    </div>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title" data-icon="📊">Usage Growth Expectations</h2>
                <table class="impact-table">
                    <thead>
                        <tr>
                            <th>Metric</th>
                            <th>Current</th>
                            <th>6 Months</th>
                            <th>1 Year</th>
                            <th>2 Years</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td><strong>Daily Active Users</strong></td>
                            <td><input type="number" style="width: 100px;"></td>
                            <td><input type="number" style="width: 100px;"></td>
                            <td><input type="number" style="width: 100px;"></td>
                            <td><input type="number" style="width: 100px;"></td>
                        </tr>
                        <tr>
                            <td><strong>Peak Concurrent Users</strong></td>
                            <td><input type="number" style="width: 100px;"></td>
                            <td><input type="number" style="width: 100px;"></td>
                            <td><input type="number" style="width: 100px;"></td>
                            <td><input type="number" style="width: 100px;"></td>
                        </tr>
                        <tr>
                            <td><strong>Daily Transactions</strong></td>
                            <td><input type="number" style="width: 100px;"></td>
                            <td><input type="number" style="width: 100px;"></td>
                            <td><input type="number" style="width: 100px;"></td>
                            <td><input type="number" style="width: 100px;"></td>
                        </tr>
                        <tr>
                            <td><strong>Monthly New Users</strong></td>
                            <td><input type="number" style="width: 100px;"></td>
                            <td><input type="number" style="width: 100px;"></td>
                            <td><input type="number" style="width: 100px;"></td>
                            <td><input type="number" style="width: 100px;"></td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <div class="section">
                <h2 class="section-title" data-icon="💼">Business Impact Assessment</h2>
                <h3>🚨 What Happens if the System is Slow?</h3>
                <p style="margin-bottom: 20px; color: #666;">Rate the impact (1 = Minor annoyance, 5 = Business critical)</p>
                
                <table class="impact-table">
                    <thead>
                        <tr>
                            <th>Impact Area</th>
                            <th>Rating</th>
                            <th>Details</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td><strong>💰 Revenue Loss</strong></td>
                            <td>
                                <div class="star-rating">
                                    <input type="radio" id="revenue-1" name="revenue-impact" value="1">
                                    <label for="revenue-1">⭐</label>
                                    <input type="radio" id="revenue-2" name="revenue-impact" value="2">
                                    <label for="revenue-2">⭐</label>
                                    <input type="radio" id="revenue-3" name="revenue-impact" value="3">
                                    <label for="revenue-3">⭐</label>
                                    <input type="radio" id="revenue-4" name="revenue-impact" value="4">
                                    <label for="revenue-4">⭐</label>
                                    <input type="radio" id="revenue-5" name="revenue-impact" value="5">
                                    <label for="revenue-5">⭐</label>
                                </div>
                            </td>
                            <td><input type="text" placeholder="$ ____ per hour of slowness" style="width: 200px;"></td>
                        </tr>
                        <tr>
                            <td><strong>😊 Customer Satisfaction</strong></td>
                            <td>
                                <div class="star-rating">
                                    <input type="radio" id="customer-1" name="customer-impact" value="1">
                                    <label for="customer-1">⭐</label>
                                    <input type="radio" id="customer-2" name="customer-impact" value="2">
                                    <label for="customer-2">⭐</label>
                                    <input type="radio" id="customer-3" name="customer-impact" value="3">
                                    <label for="customer-3">⭐</label>
                                    <input type="radio" id="customer-4" name="customer-impact" value="4">
                                    <label for="customer-4">⭐</label>
                                    <input type="radio" id="customer-5" name="customer-impact" value="5">
                                    <label for="customer-5">⭐</label>
                                </div>
                            </td>
                            <td><input type="text" placeholder="Expected complaints/feedback" style="width: 200px;"></td>
                        </tr>
                        <tr>
                            <td><strong>⚙️ Operations</strong></td>
                            <td>
                                <div class="star-rating">
                                    <input type="radio" id="operations-1" name="operations-impact" value="1">
                                    <label for="operations-1">⭐</label>
                                    <input type="radio" id="operations-2" name="operations-impact" value="2">
                                    <label for="operations-2">⭐</label>
                                    <input type="radio" id="operations-3" name="operations-impact" value="3">
                                    <label for="operations-3">⭐</label>
                                    <input type="radio" id="operations-4" name="operations-impact" value="4">
                                    <label for="operations-4">⭐</label>
                                    <input type="radio" id="operations-5" name="operations-impact" value="5">
                                    <label for="operations-5">⭐</label>
                                </div>
                            </td>
                            <td><input type="text" placeholder="Which processes stop?" style="width: 200px;"></td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <div class="section">
                <h2 class="section-title" data-icon="🎯">Performance Targets</h2>
                <div class="form-grid">
                    <div class="form-group">
                        <label for="page-load-time">Page/Screen loads in:</label>
                        <input type="number" id="page-load-time" name="page-load-time" placeholder="seconds" step="0.1">
                    </div>
                    <div class="form-group">
                        <label for="transaction-time">Transaction completes in:</label>
                        <input type="number" id="transaction-time" name="transaction-time" placeholder="seconds" step="0.1">
                    </div>
                    <div class="form-group">
                        <label for="uptime">System available:</label>
                        <input type="number" id="uptime" name="uptime" placeholder="% of time" min="0" max="100">
                    </div>
                    <div class="form-group">
                        <label for="concurrent-users">Can handle ___ users simultaneously:</label>
                        <input type="number" id="concurrent-users" name="concurrent-users" placeholder="number of users">
                    </div>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title" data-icon="🔍">Risk Areas & Concerns</h2>
                <div class="form-group">
                    <label for="main-concerns">What keeps you up at night about this system's performance?</label>
                    <textarea id="main-concerns" name="main-concerns" rows="4" placeholder="Example: I'm worried that when we launch our new promotion, the payment system will crash and we'll lose sales."></textarea>
                </div>
                
                <h3>🚨 High-Risk Scenarios</h3>
                <div class="checkbox-grid">
                    <div class="checkbox-item">
                        <input type="checkbox" id="black-friday" name="risk-scenarios" value="black-friday">
                        <label for="black-friday">Black Friday/Holiday Sales</label>
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" id="product-launches" name="risk-scenarios" value="product-launches">
                        <label for="product-launches">Product Launches</label>
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" id="marketing-campaigns" name="risk-scenarios" value="marketing-campaigns">
                        <label for="marketing-campaigns">Marketing Campaigns</label>
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" id="end-period" name="risk-scenarios" value="end-period">
                        <label for="end-period">End-of-Period Processing</label>
                    </div>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title" data-icon="📅">Timeline & Resources</h2>
                <div class="form-grid">
                    <div class="form-group">
                        <label for="testing-deadline">When must testing be complete?</label>
                        <input type="date" id="testing-deadline" name="testing-deadline">
                    </div>
                    <div class="form-group">
                        <label for="go-live-date">When is go-live date?</label>
                        <input type="date" id="go-live-date" name="go-live-date">
                    </div>
                    <div class="form-group">
                        <label for="hard-deadlines">Any hard deadlines we cannot miss?</label>
                        <input type="text" id="hard-deadlines" name="hard-deadlines" placeholder="Marketing launches, regulatory dates, etc.">
                    </div>
                    <div class="form-group">
                        <label for="technical-contact">Who can answer technical questions?</label>
                        <input type="text" id="technical-contact" name="technical-contact">
                    </div>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title" data-icon="🏆">Success Criteria</h2>
                <div class="form-group">
                    <label for="success-definition">What would make this project a complete success?</label>
                    <textarea id="success-definition" name="success-definition" rows="4" placeholder="Example: If customers can complete their purchases quickly during our busiest sales period without any issues, and we have zero performance-related complaints."></textarea>
                </div>
                
                <h3>✅ Success Indicators</h3>
                <div class="checkbox-grid">
                    <div class="checkbox-item">
                        <input type="checkbox" id="no-complaints" name="success-indicators" value="no-complaints">
                        <label for="no-complaints">No user complaints about speed</label>
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" id="handles-load" name="success-indicators" value="handles-load">
                        <label for="handles-load">System handles expected load</label>
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" id="meets-targets" name="success-indicators" value="meets-targets">
                        <label for="meets-targets">Response times meet targets</label>
                    </div>
                    <div class="checkbox-item">
                        <input type="checkbox" id="no-crashes" name="success-indicators" value="no-crashes">
                        <label for="no-crashes">No system crashes/downtime</label>
                    </div>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title" data-icon="✅">What Happens Next</h2>
                <div class="timeline-item">
                    <div class="timeline-icon">1</div>
                    <div class="timeline-content">
                        <h4>Review & Follow-up</h4>
                        <p>We'll review your submission and schedule a discussion within 2 business days</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-icon">2</div>
                    <div class="timeline-content">
                        <h4>Strategy Session</h4>
                        <p>60-minute session to deep-dive into your requirements and create a tailored testing strategy</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-icon">3</div>
                    <div class="timeline-content">
                        <h4>Detailed Proposal</h4>
                        <p>Comprehensive test plan with timelines, risk assessments, and success metrics</p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-icon">4</div>
                    <div class="timeline-content">
                        <h4>Execution & Results</h4>
                        <p>Professional testing execution with regular updates and actionable recommendations</p>
                    </div>
                </div>
            </div>

            <div class="section">
                <h2 class="section-title" data-icon="💡">Pro Tips for Better Results</h2>
                <div class="tips-grid">
                    <div class="tip-card">
                        <h4>🎯 Be Honest About</h4>
                        <ul>
                            <li>Realistic user numbers (don't underestimate)</li>
                            <li>True business impact (helps us prioritize)</li>
                            <li>Timeline constraints (we can adjust approach)</li>
                            <li>Budget limitations (we can phase testing)</li>
                        </ul>
                    </div>
                    <div class="tip-card">
                        <h4>😌 Don't Worry If You Don't Know</h4>
                        <ul>
                            <li>Technical details (we'll figure those out)</li>
                            <li>Exact numbers (estimates are fine)</li>
                            <li>How things work (we'll learn together)</li>
                            <li>Perfect specifications (we'll refine iteratively)</li>
                        </ul>
                    </div>
                    <div class="tip-card">
                        <h4>🤔 Think About</h4>
                        <ul>
                            <li>Worst-case scenarios (what could go wrong?)</li>
                            <li>Business growth (plan for success)</li>
                            <li>User frustration points (what annoys them?)</li>
                            <li>Competitive advantage (how does speed help?)</li>
                        </ul>
                    </div>
                </div>
            </div>

            <div class="contact-card">
                <h3>📞 Need Help Completing This Form?</h3>
                <p>Our team is here to help! Don't hesitate to reach out if you have questions or need clarification on any section.</p>
                <div style="margin-top: 15px;">
                    <strong>Performance Testing Team:</strong> testing@company.com | (555) 123-4567
                </div>
            </div>

            <div class="submit-section">
                <h2>🚀 Ready to Launch?</h2>
                <p>Thank you for taking the time to help us understand your performance testing needs. This information enables us to create the most effective testing strategy for your business success.</p>
                <div class="progress-bar">
                    <div class="progress-fill" style="width: 100%;"></div>
                </div>
                <p><strong>Form Complete!</strong> We'll follow up within 2 business days.</p>
                <button type="submit" class="submit-btn">🎯 Submit My Requirements</button>
            </div>
        </div>
    </div>

    <script>
        // Add some interactive elements
        document.addEventListener('DOMContentLoaded', function() {
            // Star rating functionality
            const starRatings = document.querySelectorAll('.star-rating');
            starRatings.forEach(rating => {
                const stars = rating.querySelectorAll('label');
                stars.forEach((star, index) => {
                    star.addEventListener('click', () => {
                        stars.forEach((s, i) => {
                            s.style.color = i <= index ? '#ffc107' : '#ddd';
                        });
                    });
                });
            });

            // Form progress tracking
            const formInputs = document.querySelectorAll('input[required], textarea[required]');
            const progressBar = document.querySelector('.progress-fill');
            
            function updateProgress() {
                const filledInputs = Array.from(formInputs).filter(input => input.value.trim() !== '');
                const progress = (filledInputs.length / formInputs.length) * 100;
                progressBar.style.width = progress + '%';
            }

            formInputs.forEach(input => {
                input.addEventListener('input', updateProgress);
            });

            // Checkbox interactions
            const checkboxItems = document.querySelectorAll('.checkbox-item');
            checkboxItems.forEach(item => {
                const checkbox = item.querySelector('input[type="checkbox"]');
                item.addEventListener('click', (e) => {
                    if (e.target.type !== 'checkbox' && e.target.type !== 'text' && e.target.type !== 'number') {
                        checkbox.checked = !checkbox.checked;
                    }
                });
            });

            // Smooth scrolling for sections
            const sections = document.querySelectorAll('.section');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            });

            sections.forEach(section => {
                section.style.opacity = '0';
                section.style.transform = 'translateY(20px)';
                section.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
                observer.observe(section);
            });

            // Submit button interaction
            const submitBtn = document.querySelector('.submit-btn');
            submitBtn.addEventListener('click', (e) => {
                e.preventDefault();
                submitBtn.innerHTML = '🎉 Thank You! We\'ll Be In Touch Soon';
                submitBtn.style.background = '#4CAF50';
                submitBtn.style.color = 'white';
                
                // Add celebration animation
                document.body.style.background = 'linear-gradient(135deg, #4CAF50 0%, #45a049 100%)';
                
                setTimeout(() => {
                    alert('🎯 Form submitted successfully! We\'ll review your requirements and get back to you within 2 business days.');
                }, 500);
            });

            // Auto-save functionality (local storage)
            const saveFormData = () => {
                const formData = {};
                const inputs = document.querySelectorAll('input, textarea, select');
                inputs.forEach(input => {
                    if (input.type === 'checkbox' || input.type === 'radio') {
                        formData[input.name] = input.checked;
                    } else {
                        formData[input.name] = input.value;
                    }
                });
                localStorage.setItem('perfTestingForm', JSON.stringify(formData));
            };

            const loadFormData = () => {
                const savedData = localStorage.getItem('perfTestingForm');
                if (savedData) {
                    const formData = JSON.parse(savedData);
                    Object.keys(formData).forEach(key => {
                        const input = document.querySelector(`[name="${key}"]`);
                        if (input) {
                            if (input.type === 'checkbox' || input.type === 'radio') {
                                input.checked = formData[key];
                            } else {
                                input.value = formData[key];
                            }
                        }
                    });
                }
            };

            // Load saved data on page load
            loadFormData();

            // Save data on input change
            const allInputs = document.querySelectorAll('input, textarea, select');
            allInputs.forEach(input => {
                input.addEventListener('change', saveFormData);
                input.addEventListener('input', saveFormData);
            });
        });
    </script>
</body>
</html>