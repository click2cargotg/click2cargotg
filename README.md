<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Click2Cargo Logistics | Enterprise B2B Cold Chain Leasing</title>
    <style>
        :root { 
            --primary-navy: #0A192F; 
            --secondary-blue: #172A45; 
            --accent-orange: #FF6B35; 
            --accent-hover: #E05523;
            --text-light: #F4F6F9; 
            --text-muted: #8892B0;
            --text-dark: #0A192F; 
            --card-bg: #FFFFFF; 
            --bg-light: #F8FAFC;
            --border-color: #E2E8F0;
            --success-green: #10B981;
        }
        
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', -apple-system, BlinkMacSystemFont, Roboto, sans-serif; }
        body { color: var(--text-dark); background-color: var(--bg-light); line-height: 1.6; }
        
        /* Top Utility Bar */
        .utility-bar { background: #060F1E; color: var(--text-muted); padding: 8px 8%; font-size: 13px; display: flex; justify-content: space-between; align-items: center; border-bottom: 1px solid rgba(255,255,255,0.05); flex-wrap: wrap; gap: 10px; }
        .utility-contacts span { margin-right: 15px; }
        .utility-contacts a { color: var(--accent-orange); text-decoration: none; font-weight: 600; }

        /* Header & Navigation */
        header { background: var(--primary-navy); color: white; padding: 18px 8%; display: flex; flex-direction: column; align-items: center; gap: 15px; position: sticky; top: 0; z-index: 1000; box-shadow: 0 4px 20px rgba(0,0,0,0.15); }
        @media(min-width: 768px) { header { flex-direction: row; justify-content: space-between; } }
        
        .logo-container { display: flex; align-items: center; gap: 12px; }
        .logo { font-size: 28px; font-weight: 800; letter-spacing: -0.5px; }
        .logo span { color: var(--accent-orange); }
        
        .udyam-badge { background: rgba(255,107,53,0.15); padding: 6px 14px; border-radius: 20px; font-size: 12px; border: 1px solid var(--accent-orange); color: var(--accent-orange); font-weight: 600; display: inline-flex; align-items: center; gap: 6px; }
        
        nav { display: flex; gap: 6px; flex-wrap: wrap; justify-content: center; }
        .nav-tab { background: transparent; color: #A8B2D1; border: none; padding: 10px 18px; cursor: pointer; border-radius: 6px; font-weight: 600; font-size: 14px; transition: all 0.2s ease; }
        .nav-tab:hover, .nav-tab.active { color: #FFFFFF; background: rgba(255,107,53,0.18); color: var(--accent-orange); }
        
        /* Layout Sections */
        .page-content { display: none; padding: 40px 8%; max-width: 1280px; margin: 0 auto; min-height: 70vh; opacity: 0; transition: opacity 0.3s ease; }
        .page-content.active-page { display: block; opacity: 1; }
        
        /* Hero Banner */
        .hero { 
            background: linear-gradient(135deg, rgba(10, 25, 47, 0.94), rgba(23, 42, 69, 0.9)), url('https://images.unsplash.com/photo-1586528116311-ad8dd3c8310d?auto=format&fit=crop&w=1600&q=80') center/cover no-repeat; 
            color: white; 
            padding: 80px 6%; 
            border-radius: 16px; 
            margin-bottom: 40px; 
            box-shadow: 0 10px 30px rgba(10, 25, 47, 0.2);
            position: relative;
            overflow: hidden;
        }
        .hero::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 4px; background: linear-gradient(90deg, var(--accent-orange), #FF9F1C); }
        .hero h1 { font-size: 40px; margin-bottom: 18px; font-weight: 800; line-height: 1.25; max-width: 900px; }
        @media(max-width: 768px) { .hero h1 { font-size: 28px; } }
        .hero p { font-size: 18px; max-width: 750px; margin: 0 0 30px; color: #A8B2D1; line-height: 1.6; }
        .hero-actions { display: flex; gap: 15px; flex-wrap: wrap; }
        
        /* Buttons */
        .cta-btn { background: var(--accent-orange); color: white; padding: 14px 32px; text-decoration: none; border-radius: 6px; display: inline-flex; align-items: center; gap: 8px; cursor: pointer; border: none; font-size: 15px; font-weight: 700; transition: all 0.2s; box-shadow: 0 4px 14px rgba(255,107,53,0.3); }
        .cta-btn:hover { background: var(--accent-hover); transform: translateY(-2px); }
        .whatsapp-btn { background: #25D366; color: white; }
        .whatsapp-btn:hover { background: #1EBE5D; }
        .btn-outline { background: transparent; color: white; border: 1.5px solid rgba(255,255,255,0.3); }
        .btn-outline:hover { background: rgba(255,255,255,0.1); border-color: white; }

        /* Grid Layouts */
        .grid-layout { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 24px; margin-top: 25px; }
        
        .info-card { 
            background: var(--card-bg); 
            padding: 32px; 
            border-radius: 12px; 
            border-top: 4px solid var(--primary-navy); 
            box-shadow: 0 4px 15px rgba(0,0,0,0.04); 
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }
        .info-card:hover { transform: translateY(-3px); box-shadow: 0 8px 25px rgba(0,0,0,0.08); }
        .info-card h3 { font-size: 20px; color: var(--primary-navy); margin-bottom: 12px; display: flex; align-items: center; gap: 10px; }
        .info-card p { color: #4A5568; font-size: 15px; }

        /* Editable Fields */
        .edit-field { padding: 3px 6px; border-radius: 4px; transition: 0.3s; }
        .edit-field[contenteditable="true"] { border: 1.5px dashed var(--accent-orange); background: #FFFDE7; color: #000; outline: none; }
        
        /* Counter Banner */
        .counter-section { 
            background: linear-gradient(90deg, var(--primary-navy), var(--secondary-blue)); 
            color: white; 
            padding: 24px 30px; 
            text-align: center; 
            border-radius: 12px; 
            margin: 20px 0 35px; 
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            gap: 20px;
            box-shadow: 0 4px 15px rgba(10,25,47,0.1);
        }
        .counter-badge { display: flex; align-items: center; gap: 15px; text-align: left; }
        .counter-number { font-size: 36px; font-weight: 800; color: var(--accent-orange); font-family: monospace; letter-spacing: 2px; }

        /* Admin Box */
        .admin-login-box { background: #FFFFFF; border: 1px solid var(--border-color); padding: 24px; text-align: center; max-width: 360px; margin: 30px auto; border-radius: 12px; box-shadow: 0 4px 15px rgba(0,0,0,0.05); }
        .admin-input { padding: 12px; width: 100%; margin-bottom: 12px; border: 1px solid var(--border-color); border-radius: 6px; text-align: center; font-size: 14px; }
        .admin-btn { background: var(--primary-navy); color: white; border: none; padding: 12px 18px; cursor: pointer; border-radius: 6px; width: 100%; font-weight: 700; transition: background 0.2s; }
        .admin-btn:hover { background: var(--secondary-blue); }
        .editor-notice { display: none; background: #DEF7EC; color: #03543F; border: 1px solid #84E1BC; padding: 14px 20px; text-align: center; border-radius: 8px; font-weight: 600; font-size: 14px; margin-bottom: 25px; }

        /* Form Styles */
        .quote-form { background: white; padding: 36px; border-radius: 12px; box-shadow: 0 4px 20px rgba(0,0,0,0.06); border: 1px solid var(--border-color); }
        .form-row { display: grid; grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)); gap: 20px; margin-bottom: 18px; }
        .form-group { margin-bottom: 18px; text-align: left; }
        .form-group label { display: block; font-weight: 700; margin-bottom: 6px; color: var(--primary-navy); font-size: 14px; }
        .form-control { width: 100%; padding: 12px 14px; border: 1px solid var(--border-color); border-radius: 6px; font-size: 15px; outline: none; transition: border-color 0.2s; }
        .form-control:focus { border-color: var(--accent-orange); box-shadow: 0 0 0 3px rgba(255,107,53,0.12); }

        /* Interactive Calculator Widget */
        .calc-box { background: #F1F5F9; border: 1px solid #CBD5E1; padding: 24px; border-radius: 10px; margin: 25px 0; }
        .calc-result { background: var(--primary-navy); color: white; padding: 20px; border-radius: 8px; text-align: center; margin-top: 15px; }
        .calc-price { font-size: 32px; font-weight: 800; color: var(--accent-orange); }

        /* Route Tags */
        .route-pill { display: inline-block; background: #E2E8F0; color: #334155; padding: 6px 14px; border-radius: 20px; font-size: 13px; font-weight: 600; margin: 4px; }
        .route-pill.highlight { background: rgba(255,107,53,0.15); color: var(--accent-orange); border: 1px solid rgba(255,107,53,0.3); }

        /* Temperature Slider Widget */
        .temp-slider-container { background: white; padding: 30px; border-radius: 12px; border: 1px solid var(--border-color); margin: 30px 0; }
        .temp-display { font-size: 28px; font-weight: 800; color: var(--primary-navy); margin: 10px 0; text-align: center; }

        /* Toast Notifications */
        #toast { visibility: hidden; min-width: 280px; background-color: #1E293B; color: #fff; text-align: center; border-radius: 8px; padding: 14px 24px; position: fixed; z-index: 2000; left: 50%; bottom: 30px; transform: translateX(-50%); font-size: 15px; font-weight: 600; box-shadow: 0 10px 25px rgba(0,0,0,0.2); opacity: 0; transition: opacity 0.3s, visibility 0.3s; }
        #toast.show { visibility: visible; opacity: 1; }

        footer { background: #060F1E; color: var(--text-muted); padding: 50px 8% 30px; margin-top: 80px; border-top: 1px solid rgba(255,255,255,0.05); }
        .footer-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 40px; margin-bottom: 40px; text-align: left; }
        .footer-col h4 { color: white; font-size: 16px; margin-bottom: 18px; font-weight: 700; }
        .footer-col p, .footer-col a { color: #8892B0; font-size: 14px; text-decoration: none; display: block; margin-bottom: 8px; }
        .footer-col a:hover { color: var(--accent-orange); }
        .copyright { text-align: center; border-top: 1px solid rgba(255,255,255,0.08); padding-top: 25px; font-size: 13px; color: #8892B0; }
    </style>
</head>
<body>

    <!-- Utility Bar -->
    <div class="utility-bar">
        <div class="utility-contacts">
            <span>📍 Corporate Desk: Hyderabad / Secunderabad, Telangana</span>
            <span>⚡ Fleet Hotline (WhatsApp): <a href="https://wa.me/919493696175" target="_blank">+91 94936 96175</a></span>
            <span>✉️ Operations: <a href="mailto:click2cargo.tg@gmail.com">click2cargo.tg@gmail.com</a></span>
        </div>
        <div>
            <span>🛡️ Enterprise B2B Dry-Lease Operations</span>
        </div>
    </div>

    <!-- Header -->
    <header>
        <div class="logo-container">
            <div class="logo">Click2<span>Cargo</span></div>
            <div class="udyam-badge">
                🛡️ TS-REGD: <span class="edit-field" id="udyam-id">UDYAM-TS-20-0205801</span>
            </div>
        </div>
        
        <nav>
            <button class="nav-tab active" onclick="switchPage('home')">Home</button>
            <button class="nav-tab" onclick="switchPage('about')">About</button>
            <button class="nav-tab" onclick="switchPage('services')">Capabilities</button>
            <button class="nav-tab" onclick="switchPage('fleet')">Join Fleet</button>
            <button class="nav-tab" onclick="switchPage('contact')">Contact & Quote</button>
        </nav>
    </header>

    <!-- Global Stats & Admin Editor Alert -->
    <div style="max-width: 1280px; margin: 25px auto 0; padding: 0 8%;">
        <div id="success-notice" class="editor-notice">
            ✏️ <strong>2026 LIVE EDITOR UNLOCKED:</strong> Feel free to click and modify any text directly on the screen!
        </div>

        <div class="counter-section">
            <div class="counter-badge">
                <span style="font-size:32px;">📊</span>
                <div>
                    <strong style="font-size:16px;">Click2Cargo Digital Traffic & Audit Verification</strong>
                    <p style="font-size: 12px; color: #8892B0; margin-top: 2px;">Logged institutional verification requests from pharmaceutical & FMCG supply chain managers.</p>
                </div>
            </div>
            <div style="text-align: right;">
                <div class="counter-number" id="visitor-counter">14,892</div>
                <span style="font-size: 11px; text-transform: uppercase; letter-spacing: 1px; color: #A8B2D1;">Verified Corporate Impressions</span>
            </div>
        </div>
    </div>

    <!-- PAGE 1: HOME PANEL -->
    <main id="home" class="page-content active-page">
        <div class="hero">
            <h1 class="edit-field" id="hero-title">Premium Unmanned Cold Chain Infrastructure</h1>
            <p class="edit-field" id="hero-desc">Deploying factory-fresh, sub-zero refrigerated commercial vehicle assets across pharmaceutical and bio-logistics hubs in Telangana.</p>
            <div class="hero-actions">
                <button class="cta-btn" onclick="switchPage('contact')">Request Asset Allocation →</button>
                <a href="https://wa.me/919493696175" target="_blank" class="cta-btn whatsapp-btn">📱 WhatsApp Hotline Desk</a>
                <button class="cta-btn btn-outline" onclick="switchPage('services')">View Fleet Specs</button>
            </div>
        </div>
        
        <h2 class="edit-field" id="sec1-t" style="margin-top:20px; font-size: 24px; color: var(--primary-navy);">1. Core B2B Operating Framework</h2>
        <div class="grid-layout">
            <div class="info-card">
                <h3>🚚 <span class="edit-field" id="card1-title">Asset-Light Leasing Model</span></h3>
                <p class="edit-field" id="card1-desc">We strictly provision the physical refrigerated asset (vehicles with certified reefer units). The enterprise lessee manages driver allocation and fuel parameters independently.</p>
            </div>
            <div class="info-card">
                <h3>🛡️ <span class="edit-field" id="card2-title">Zero Overhead Liability</span></h3>
                <p class="edit-field" id="card2-desc">Eliminate driver absenteeism risks, labor regulatory liabilities, operational disputes, and unpredictable chassis maintenance overheads completely.</p>
            </div>
            <div class="info-card">
                <h3>❄️ <span class="edit-field" id="card3-title">Factory-Fresh Reefers</span></h3>
                <p class="edit-field" id="card3-desc">100% compliant multi-temperature container units featuring high-density PUF insulation, standby power ports, and automated dataloggers.</p>
            </div>
        </div>

        <!-- Interactive Temperature Range Selector -->
        <h2 class="edit-field" id="sec2-t" style="margin-top:50px; font-size: 24px; color: var(--primary-navy);">2. Precision Temperature Compliance Selector</h2>
        
        <div class="temp-slider-container">
            <p style="text-align: center; font-weight: 600; color: #64748B;">Drag the slider to test container temperature settings for your cargo:</p>
            <div class="temp-display" id="temp-val-display">+4°C (Chilled Fleet)</div>
            <input type="range" min="-25" max="25" value="4" style="width: 100%; accent-color: var(--accent-orange); cursor: pointer;" id="temp-slider" oninput="updateTempSim(this.value)">
            
            <div style="margin-top: 20px; background: #F8FAFC; padding: 20px; border-radius: 8px; text-align: center;" id="temp-info-box">
                <strong style="color: var(--primary-navy); font-size: 18px;" id="temp-category">Chilled Pharmaceutical & Vaccines (+2°C to +8°C)</strong>
                <p style="margin-top: 8px; color: #475569;" id="temp-desc">Engineered strictly for critical pharmaceutical vaccines, biological samples, insulin, fresh dairy supplies, and specialty clinical reagents.</p>
            </div>
        </div>

        <div class="grid-layout">
            <div class="info-card" style="border-top-color: #3182CE;">
                <h3>🌡️ <span class="edit-field" id="temp1-h">Controlled Ambient (+15°C to +25°C)</span></h3>
                <p class="edit-field" id="temp1-d">Optimized for specialized tablet blister packs, medical devices, syrups, and temperature-sensitive cosmetics supply configurations.</p>
            </div>
            <div class="info-card" style="border-top-color: #319795;">
                <h3>❄️ <span class="edit-field" id="temp2-h">Chilled Fleet (+2°C to +8°C)</span></h3>
                <p class="edit-field" id="temp2-d">Engineered strictly for critical pharmaceutical vaccines, biological samples, dairy supplies, and fresh agricultural export logistics.</p>
            </div>
            <div class="info-card" style="border-top-color: var(--accent-orange);">
                <h3>🧊 <span class="edit-field" id="temp3-h">Deep Frozen (-20°C to -25°C)</span></h3>
                <p class="edit-field" id="temp3-d">Heavy-duty variable compression units built for bulk ice cream, frozen protein distribution, and specialized chemical testing elements.</p>
            </div>
        </div>
    </main>

    <!-- PAGE 2: ABOUT THE FOUNDER & YOUTH EMPOWERMENT -->
    <main id="about" class="page-content">
        <h2 class="edit-field" id="about-title" style="font-size: 28px; color: var(--primary-navy); margin-bottom: 20px;">Leadership Profile & Vision</h2>
        
        <div class="info-card" style="line-height: 1.8; margin-bottom: 40px; border-top: 4px solid var(--accent-orange);">
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 30px; align-items: center; margin-bottom: 25px;">
                <div style="text-align: center; position: relative;">
                    <img src="founder.jpeg" alt="Gaganam Ravikumar - Founder & Managing Director" style="width: 100%; max-width: 320px; border-radius: 12px; box-shadow: 0 10px 25px rgba(10,25,47,0.2); border: 3px solid var(--primary-navy); display: block; margin: 0 auto;" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1560250097-0b93528c311a?auto=format&fit=crop&w=600&q=80';">
                    <div style="margin-top: 14px; background: rgba(10, 25, 47, 0.05); padding: 8px 14px; border-radius: 8px; border: 1px dashed var(--accent-orange);">
                        <strong style="color: var(--primary-navy); font-size: 13px; text-transform: uppercase; letter-spacing: 0.5px;">"Logistics Built on Human Purpose"</strong>
                    </div>
                </div>
                <div>
                    <h3 class="edit-field" id="founder-name" style="margin: 0; font-size: 28px; color: var(--primary-navy);">Gaganam Ravikumar</h3>
                    <p style="font-weight: 700; color: var(--accent-orange); font-size: 16px; margin-bottom: 15px;" class="edit-field" id="founder-title">Founder & Managing Director | Click2Cargo Logistics</p>
                    
                    <div style="background: #F8FAFC; padding: 16px 20px; border-left: 4px solid var(--accent-orange); border-radius: 0 8px 8px 0; margin-bottom: 15px;">
                        <p style="font-style: italic; color: #334155; font-size: 15px; margin: 0;">
                            "Your supply chain can do more than move cargo. Discover the mission within. We build logistics not just with cold-chain assets, but on human purpose."
                        </p>
                    </div>

                    <p class="edit-field" id="founder-vision-1" style="color: #4A5568; margin-bottom: 12px;">
                        Gaganam Ravikumar is a visionary logistics entrepreneur and social impact advocate based in Telangana. Identifying critical vulnerabilities in traditional cold-chain networks—such as driver absenteeism, vehicle downtime, and operational friction—he engineered Click2Cargo's innovative <strong>unmanned dry-lease framework</strong> to deliver zero-downtime reliability for pharmaceutical and FMCG enterprise leaders.
                    </p>
                </div>
            </div>

            <div style="border-top: 1px solid var(--border-color); padding-top: 25px; margin-top: 20px;">
                <h4 style="color: var(--primary-navy); font-size: 18px; margin-bottom: 12px;">🚀 Strategic Vision & Core Philosophy</h4>
                <p class="edit-field" id="founder-vision-2" style="color: #4A5568; margin-bottom: 15px;">
                    Under Ravikumar’s leadership, Click2Cargo has evolved beyond standard commercial fleet leasing into a mission centered on human potential. By decoupling vehicle asset deployment from driver liabilities, Click2Cargo enables corporate clients to execute precision sub-zero logistics while paving structured pathways for first-generation micro-entrepreneurs.
                </p>

                <div class="grid-layout" style="margin-top: 20px;">
                    <div style="background: #F1F5F9; padding: 18px; border-radius: 8px;">
                        <strong style="color: var(--primary-navy); display: block; margin-bottom: 5px;">📍 Purpose-Driven Cold Chain</strong>
                        <span style="font-size: 14px; color: #475569;">Pioneering sub-zero dry-lease cold storage transit across pharmaceutical corridors including Medchal, Patancheru, and RGIA Shamshabad Cargo Zone.</span>
                    </div>
                    <div style="background: #F1F5F9; padding: 18px; border-radius: 8px;">
                        <strong style="color: var(--primary-navy); display: block; margin-bottom: 5px;">🤝 Social Mobility & Youth Upliftment</strong>
                        <span style="font-size: 14px; color: #475569;">Facilitating government subsidies (T-PRIDE & Stand-Up India) to empower 100+ youth from SC/ST/BC backgrounds as asset-owning fleet partners.</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- Social Impact & Youth Empowerment -->
        <div style="background: linear-gradient(135deg, #0A192F, #172A45); color: white; padding: 36px; border-radius: 12px; margin-bottom: 40px;">
            <h2 style="color: var(--accent-orange); font-size: 24px; margin-bottom: 12px;">🌱 Empowering the Next Generation of Youth Entrepreneurs</h2>
            <p style="color: #A8B2D1; font-size: 16px; margin-bottom: 20px;">
                Are you an unemployed youth or an aspiring owner-operator holding an SC/ST/BC certificate in Telangana? Click2Cargo provides the ultimate launchpad. We help you unlock <strong>T-PRIDE</strong> and <strong>Stand-Up India</strong> subsidies to secure your asset and attach it straight to corporate giants.
            </p>
            <div style="background: rgba(255,255,255,0.06); padding: 20px; border-radius: 8px; border-left: 4px solid var(--accent-orange); margin-bottom: 20px;">
                <strong style="font-size: 18px; color: white;">Join Our 100+ Member Network Today</strong>
                <p style="color: #CBD5E1; margin-top: 6px;">No upfront capital or budget needed. We align your future vehicle with guaranteed work orders.</p>
            </div>
            <a href="https://wa.me/919493696175?text=Hello%20Click2Cargo,%20I%20am%20interested%20in%20joining%20the%20Youth%20Entrepreneurship%20T-PRIDE%20Network." target="_blank" class="cta-btn whatsapp-btn" style="text-decoration: none;">🔗 Submit Details via WhatsApp Desk</a>
        </div>
        
        <h2 class="edit-field" id="route-h" style="font-size: 24px; color: var(--primary-navy); margin-top:40px;">Primary Telangana Cold Transit Corridors</h2>
        <p style="color: var(--text-muted); margin-bottom: 20px;">Click2Cargo assets are optimized for continuous shuttle operations along key industrial belts:</p>
        
        <div class="grid-layout">
            <div class="info-card" style="border-top-color: var(--accent-orange);">
                <h3>🚚 Medchal & Kompally Stretch</h3>
                <p>Serving the heaviest FMCG and e-commerce cold-chain redistribution warehouses along NH-44.</p>
                <div style="margin-top: 15px;">
                    <span class="route-pill highlight">Medchal</span>
                    <span class="route-pill">Kompally</span>
                    <span class="route-pill highlight">NH-44 Belt</span>
                </div>
            </div>
            <div class="info-card" style="border-top-color: var(--primary-navy);">
                <h3>🏭 Patancheru & Pashamylaram</h3>
                <p>Providing dedicated pharmaceutical line-haul reefer assets for global bulk drug manufacturers.</p>
                <div style="margin-top: 15px;">
                    <span class="route-pill highlight">Patancheru</span>
                    <span class="route-pill">Pashamylaram</span>
                    <span class="route-pill">Bollaram</span>
                </div>
            </div>
            <div class="info-card" style="border-top-color: #319795;">
                <h3>✈️ Shamshabad Cargo Zone</h3>
                <p>Direct airport tarmac-side connections for time-critical, international export vaccine handling.</p>
                <div style="margin-top: 15px;">
                    <span class="route-pill highlight">RGIA Cargo</span>
                    <span class="route-pill">Shamshabad</span>
                    <span class="route-pill">Tarmac Express</span>
                </div>
            </div>
        </div>
    </main>

    <!-- PAGE 3: CAPABILITIES & SERVICES -->
    <main id="services" class="page-content">
        <h2 style="font-size: 28px; color: var(--primary-navy); margin-bottom: 10px;">Industrial Cold Chain Capabilities</h2>
        <p style="color: var(--text-muted); margin-bottom: 30px;">Commercial reefer specifications built for strict pharmaceutical audits and cold storage integrity.</p>

        <div class="grid-layout" style="margin-bottom: 40px;">
            <div class="info-card" style="border-top-color: var(--accent-orange);">
                <h3>📜 GDP Compliant Logistics</h3>
                <p>Our asset deployment frame meets strict global Good Distribution Practices for pharmaceutical transport safety.</p>
            </div>
            <div class="info-card" style="border-top-color: var(--success-green);">
                <h3>📜 FSSAI Storage Alignments</h3>
                <p>Reefer box materials and insulation barriers strictly adhere to national food-grade handling sanitation rules.</p>
            </div>
        </div>

        <h3 style="font-size: 22px; color: var(--primary-navy); margin-bottom: 20px;">Reefer Vehicle Fleet Segments</h3>
        <div class="grid-layout">
            <div class="info-card">
                <h3>🚐 Small Segment</h3>
                <p style="margin-bottom: 10px;"><strong>Models:</strong> Mahindra Zeo / Tata Ace Reefer</p>
                <p style="margin-bottom: 10px;"><strong>Payload Capacity:</strong> 1.0 to 1.5 Tons</p>
                <p style="margin-bottom: 10px;"><strong>Temp Range:</strong> -18°C to +15°C</p>
                <p style="font-size: 13px; color: var(--accent-orange); font-weight: 700;">Best for intra-city vaccine & pharmacy last-mile delivery.</p>
            </div>
            <div class="info-card">
                <h3>🚚 Mid-Mile Pickup Segment</h3>
                <p style="margin-bottom: 10px;"><strong>Models:</strong> Mahindra Bolero Pickup Reefer</p>
                <p style="margin-bottom: 10px;"><strong>Payload Capacity:</strong> 2.5 to 3.5 Tons</p>
                <p style="margin-bottom: 10px;"><strong>Temp Range:</strong> -25°C to +25°C</p>
                <p style="font-size: 13px; color: var(--accent-orange); font-weight: 700;">Ideal for inter-district pharma shuttles & dairy supply.</p>
            </div>
            <div class="info-card">
                <h3>🚛 Heavy Segment</h3>
                <p style="margin-bottom: 10px;"><strong>Models:</strong> Eicher Pro Reefer Truck (14ft to 32ft)</p>
                <p style="margin-bottom: 10px;"><strong>Payload Capacity:</strong> 7 to 20 Tons</p>
                <p style="margin-bottom: 10px;"><strong>Temp Range:</strong> Sub-zero deep freeze dual compressor</p>
                <p style="font-size: 13px; color: var(--accent-orange); font-weight: 700;">Built for bulk pharmaceutical export shipments & airport logistics.</p>
            </div>
        </div>

        <div style="margin-top: 40px; background: white; padding: 30px; border-radius: 12px; border: 1px solid var(--border-color);">
            <h3 style="color: var(--primary-navy); margin-bottom: 15px;">📡 4. Advanced IoT Telematics Ready</h3>
            <p style="color: #475569; line-height: 1.8; margin-bottom: 15px;">
                Even under our unmanned dry-lease model, every Click2Cargo asset comes integrated with specialized digital data loggers and smart GPS hardware. This enables corporate lessees to sync our vehicles straight into their internal tracking dashboards to monitor real-time temperature logs and transit maps flawlessly.
            </p>
            <ul style="padding-left: 20px; color: #475569; line-height: 1.8;">
                <li><strong>Continuous Thermal Logging:</strong> Real-time temperature sensors with Bluetooth & GSM dataloggers.</li>
                <li><strong>Remote Door Open Alerts:</strong> Digital latch monitors preventing unauthorized thermal leaks.</li>
                <li><strong>Dual Power Standby:</strong> Electric plug-in standby compressors for stationary dock loading.</li>
                <li><strong>WHO-GDP Compliant:</strong> Calibration certificates provided with every dry-lease contract.</li>
            </ul>
        </div>
    </main>

    <!-- PAGE 4: JOIN FLEET -->
    <main id="fleet" class="page-content">
        <h2 style="font-size: 28px; color: var(--primary-navy); margin-bottom: 10px;">Partner With Click2Cargo Fleet</h2>
        <p style="color: var(--text-muted); margin-bottom: 30px;">Attach your commercial refrigerated vehicle or join our driver-partner ecosystem in Telangana.</p>

        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 30px;">
            <div class="quote-form">
                <h3 style="color: var(--primary-navy); margin-bottom: 20px;">Fleet Onboarding Application</h3>
                <form id="partner-form" onsubmit="handlePartnerSubmit(event)">
                    <div class="form-group">
                        <label>Full Name</label>
                        <input type="text" class="form-control" placeholder="Enter applicant name" required>
                    </div>
                    <div class="form-row">
                        <div class="form-group">
                            <label>Phone Number</label>
                            <input type="tel" class="form-control" placeholder="Mobile number" required>
                        </div>
                        <div class="form-group">
                            <label>District / Region</label>
                            <select class="form-control">
                                <option>Hyderabad / Ranga Reddy</option>
                                <option>Medchal-Malkajgiri</option>
                                <option>Sangareddy / Patancheru</option>
                                <option>Warangal</option>
                                <option>Other Telangana District</option>
                            </select>
                        </div>
                    </div>
                    <div class="form-group">
                        <label>Asset Category</label>
                        <select class="form-control">
                            <option>Small Segment (Mahindra Zeo / Tata Ace Reefer)</option>
                            <option>Mid-Mile Pickup Segment (Mahindra Bolero Pickup Reefer)</option>
                            <option>Heavy Segment (Eicher Pro Reefer Truck)</option>
                            <option>Commercial Driver looking for Dry-Lease operation</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Vehicle Registration Number (Optional)</label>
                        <input type="text" class="form-control" placeholder="e.g. TS 08 XX 1234">
                    </div>
                    <button type="submit" class="cta-btn" style="width: 100%; justify-content: center;">Submit Partner Application</button>
                </form>
            </div>

            <div>
                <div class="info-card" style="margin-bottom: 20px; border-top-color: var(--success-green);">
                    <h3>🤝 Why Partner With Us?</h3>
                    <ul style="padding-left: 20px; color: #475569; line-height: 1.8; margin-top: 10px;">
                        <li>Guaranteed corporate lease payouts.</li>
                        <li>Support unlocking T-PRIDE and Stand-Up India subsidies for SC/ST/BC entrepreneurs.</li>
                        <li>Long-term institutional supply contracts with leading pharma firms.</li>
                        <li>Dedicated maintenance assistance and uptime guarantees.</li>
                    </ul>
                </div>

                <div class="info-card" style="border-top-color: var(--accent-orange); text-align: center;">
                    <h3>📱 Quick Application via WhatsApp</h3>
                    <p style="margin-bottom: 15px;">Send your vehicle details directly to our fleet management team.</p>
                    <a href="https://wa.me/919493696175?text=Hi%20Click2Cargo,%20I%20want%20to%20attach%20my%20reefer%20vehicle." target="_blank" class="cta-btn whatsapp-btn" style="width: 100%; justify-content: center; text-decoration: none;">🔗 Connect on WhatsApp Desk</a>
                </div>
            </div>
        </div>
    </main>

    <!-- PAGE 5: CONTACT & INSTANT QUOTE -->
    <main id="contact" class="page-content">
        <h2 style="font-size: 28px; color: var(--primary-navy); margin-bottom: 10px;">Institutional Quote & Contact Panel</h2>
        <p style="color: var(--text-muted); margin-bottom: 30px;">Get a dry-lease asset allocation estimate tailored to your pharma or FMCG logistics schedule.</p>

        <!-- Dynamic Calculator -->
        <div class="calc-box">
            <h3 style="color: var(--primary-navy); margin-bottom: 15px;">🧮 Instant B2B Dry-Lease Estimator</h3>
            <div class="form-row">
                <div class="form-group">
                    <label>Select Vehicle Capacity</label>
                    <select class="form-control" id="calc-vehicle" onchange="calculateQuote()">
                        <option value="1.5">Small Segment (Mahindra Zeo / Tata Ace Reefer)</option>
                        <option value="3.5" selected>Mid-Mile Pickup (Mahindra Bolero Reefer)</option>
                        <option value="7.0">Heavy Segment (Eicher Pro Reefer Truck)</option>
                        <option value="15.0">15.0 Ton Multi-Axle Reefer Rig</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Lease Duration (Months)</label>
                    <select class="form-control" id="calc-duration" onchange="calculateQuote()">
                        <option value="1">1 Month Spot Allocation</option>
                        <option value="6" selected>6 Months Corporate Contract</option>
                        <option value="12">12 Months Annual Leasing (Best Rate)</option>
                    </select>
                </div>
            </div>
            <div class="calc-result">
                <span style="font-size: 13px; text-transform: uppercase; letter-spacing: 1px;">Estimated Monthly Dry-Lease Asset Rate:</span>
                <div class="calc-price" id="calc-price-output">₹ 78,000 / Mo</div>
                <span style="font-size: 12px; color: #A8B2D1;">Excludes driver & fuel liabilities. Includes reefer maintenance & IoT telemetry.</span>
            </div>
        </div>

        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 30px;">
            <div class="quote-form">
                <h3 style="color: var(--primary-navy); margin-bottom: 20px;">Request An Unmanned Asset Allocation Quote</h3>
                <form id="quote-form" onsubmit="handleQuoteSubmit(event)">
                    <div class="form-group">
                        <label>Corporate Company Name</label>
                        <input type="text" class="form-control" placeholder="e.g. Hyderabad Pharma Labs Ltd" required>
                    </div>
                    <div class="form-row">
                        <div class="form-group">
                            <label>Contact Person Name</label>
                            <input type="text" class="form-control" placeholder="Name" required>
                        </div>
                        <div class="form-group">
                            <label>Official Email</label>
                            <input type="email" class="form-control" placeholder="email@company.com" required>
                        </div>
                    </div>
                    <div class="form-row">
                        <div class="form-group">
                            <label>Phone / WhatsApp</label>
                            <input type="tel" class="form-control" placeholder="+91 94936 96175" required>
                        </div>
                        <div class="form-group">
                            <label>Required Reefer Vehicle Class</label>
                            <select class="form-control">
                                <option>Small Segment (Mahindra Zeo / Tata Ace Reefer)</option>
                                <option>Mid-Mile Pickup Segment (Mahindra Bolero Pickup Reefer)</option>
                                <option>Heavy Segment (Eicher Pro Reefer Truck)</option>
                            </select>
                        </div>
                    </div>
                    <div class="form-group">
                        <label>Target Deployment Hub / Route & Tenure (Months)</label>
                        <textarea class="form-control" rows="3" placeholder="Specify origin, destination hub, monthly km estimate, and duration..."></textarea>
                    </div>
                    <button type="submit" class="cta-btn" style="width: 100%; justify-content: center;">📊 Submit Asset Allocation Request</button>
                </form>
            </div>

            <div class="contact-panel">
                <h3 style="color: var(--primary-navy); margin-bottom: 20px;">Institutional Empanelment & Procurement Desk</h3>
                
                <div class="contact-item">
                    <strong style="display:block; color: var(--primary-navy);">Registered MSME Entity:</strong>
                    <span>Click2Cargo Logistics</span><br>
                    <span style="color: var(--accent-orange); font-weight: 700;">UDYAM-TS-20-0205801</span>
                </div>

                <div class="contact-item">
                    <strong style="display:block; color: var(--primary-navy);">Corporate HQ:</strong>
                    <span>Secunderabad / Hyderabad Hub, Telangana</span>
                </div>

                <div class="contact-item">
                    <strong style="display:block; color: var(--primary-navy);">⚡ Fleet Allocation Hotline (WhatsApp):</strong>
                    <a href="https://wa.me/919493696175" target="_blank" class="contact-link">+91 94936 96175</a>
                </div>

                <div class="contact-item">
                    <strong style="display:block; color: var(--primary-navy);">✉️ Official Operations Mailbox:</strong>
                    <a href="mailto:click2cargo.tg@gmail.com" class="contact-link">click2cargo.tg@gmail.com</a>
                </div>

                <!-- Admin Unlock Trigger -->
                <div class="admin-login-box" id="auth-box">
                    <h4 style="margin-bottom: 10px; color: var(--primary-navy);">🔐 Click2Cargo Owner Portal</h4>
                    <input type="password" id="pass-input" class="admin-input" placeholder="Enter Security Pin (2026)">
                    <button onclick="verifyOwner()" class="admin-btn">Unlock Live Editor</button>
                </div>
            </div>
        </div>
    </main>

    <!-- Toast Notification -->
    <div id="toast">Form submitted successfully!</div>

    <!-- Footer -->
    <footer>
        <div class="footer-grid">
            <div class="footer-col">
                <div class="logo" style="margin-bottom: 15px;">Click2<span>Cargo</span></div>
                <p>Enterprise B2B Cold Chain Vehicle Asset Leasing across Telangana & South India pharmaceutical hubs.</p>
                <p style="margin-top: 10px; color: var(--accent-orange); font-weight: 600;">Regd: UDYAM-TS-20-0205801</p>
            </div>
            <div class="footer-col">
                <h4>Navigation</h4>
                <a href="javascript:switchPage('home')">Home</a>
                <a href="javascript:switchPage('about')">Founder & Leadership</a>
                <a href="javascript:switchPage('services')">Capabilities</a>
                <a href="javascript:switchPage('fleet')">Join Fleet Partner</a>
                <a href="javascript:switchPage('contact')">Instant Quote</a>
            </div>
            <div class="footer-col">
                <h4>Temperature Compliance</h4>
                <p>• Controlled Ambient (+15°C to +25°C)</p>
                <p>• Vaccine & Chilled (+2°C to +8°C)</p>
                <p>• Sub-Zero Frozen (-20°C to -25°C)</p>
                <p>• Cryo Datalogger Instrumentation</p>
            </div>
            <div class="footer-col">
                <h4>Primary Telangana Belts</h4>
                <p>Medchal & Kompally Stretch (NH-44)</p>
                <p>Patancheru & Pashamylaram Bulk Hubs</p>
                <p>Shamshabad Cargo Zone (Airport Export)</p>
                <p>Shameerpet Genome Valley Corridor</p>
            </div>
        </div>
        <div class="copyright">
            <p>© 2026 Click2Cargo Logistics. Managed under Executive Supervision of Gaganam Ravikumar. All Rights Reserved.</p>
        </div>
    </footer>

    <script>
        // Modernized Page Navigation Logic
        function switchPage(pageId) {
            document.querySelectorAll('.page-content').forEach(p => p.classList.remove('active-page'));
            document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
            
            const target = document.getElementById(pageId);
            if (target) {
                target.classList.add('active-page');
            }
            
            // Highlight the clicked nav button using smart text match
            const activeTab = Array.from(document.querySelectorAll('.nav-tab')).find(tab => 
                tab.textContent.toLowerCase().includes(pageId.substring(0,3))
            );
            if(activeTab) activeTab.classList.add('active');
            
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Owner Verification to Unlock Editor
        let ownerUnlocked = false;
        function verifyOwner() {
            const pin = document.getElementById('pass-input').value;
            if(pin === '2026' || pin === 'admin') {
                ownerUnlocked = true;
                document.querySelectorAll('.edit-field').forEach(f => f.setAttribute('contenteditable', 'true'));
                document.getElementById('success-notice').style.display = 'block';
                document.getElementById('auth-box').style.display = 'none';
                showToast('✏️ Live Editor Unlocked!');
            } else { 
                showToast('Access Denied: Invalid Security Pin'); 
            }
        }

        // Temperature Simulator Widget
        function updateTempSim(val) {
            const tempVal = parseInt(val);
            const display = document.getElementById('temp-val-display');
            const category = document.getElementById('temp-category');
            const desc = document.getElementById('temp-desc');

            const formattedTemp = (tempVal > 0 ? '+' : '') + tempVal + '°C';
            display.innerText = formattedTemp;

            if(tempVal >= 15) {
                display.style.color = '#3182CE';
                category.innerText = 'Controlled Ambient (+15°C to +25°C)';
                desc.innerText = 'Optimized for specialized tablet blister packs, medical devices, syrups, and temperature-sensitive cosmetics.';
            } else if(tempVal >= 0 && tempVal < 15) {
                display.style.color = '#319795';
                category.innerText = 'Chilled Pharma & Biologicals (+2°C to +8°C)';
                desc.innerText = 'Engineered strictly for critical pharmaceutical vaccines, biological samples, insulin, dairy supplies, and fresh produce.';
            } else {
                display.style.color = '#FF6B35';
                category.innerText = 'Deep Sub-Zero Freeze (-18°C to -25°C)';
                desc.innerText = 'Heavy-duty variable compression units built for bulk ice cream, frozen protein distribution, and specialized clinical testing reagents.';
            }
        }

        // Instant B2B Quote Calculator
        function calculateQuote() {
            const vehicle = parseFloat(document.getElementById('calc-vehicle').value);
            const duration = parseInt(document.getElementById('calc-duration').value);

            let baseRate = 48000;
            if(vehicle === 1.5) baseRate = 48000;
            else if(vehicle === 3.5) baseRate = 78000;
            else if(vehicle === 7.0) baseRate = 135000;
            else if(vehicle === 15.0) baseRate = 220000;

            let discountMultiplier = 1.0;
            if(duration === 6) discountMultiplier = 0.92;
            else if(duration === 12) discountMultiplier = 0.85;

            const finalMonthlyRate = Math.round(baseRate * discountMultiplier);
            document.getElementById('calc-price-output').innerText = '₹ ' + finalMonthlyRate.toLocaleString('en-IN') + ' / Mo';
        }

        // Auto Counter Increment Logic
        function initCounter() {
            let count = 14892;
            setInterval(() => {
                count += Math.floor(Math.random() * 3) + 1;
                document.getElementById('visitor-counter').innerText = count.toLocaleString('en-IN');
            }, 8000);
        }

        // Toast Helper
        function showToast(message) {
            const toast = document.getElementById('toast');
            toast.innerText = message;
            toast.classList.add('show');
            setTimeout(() => {
                toast.classList.remove('show');
            }, 3500);
        }

        // Form Submit Handlers
        function handlePartnerSubmit(e) {
            e.preventDefault();
            showToast('✅ Fleet Partner Application Received!');
            e.target.reset();
        }

        function handleQuoteSubmit(e) {
            e.preventDefault();
            showToast('✅ Asset Allocation Request Submitted!');
            e.target.reset();
        }

        // Cache live edits to localStorage
        document.addEventListener('input', function(e) {
            if (e.target.classList.contains('edit-field') && ownerUnlocked) {
                if (e.target.id) {
                    localStorage.setItem('c2c_edit_' + e.target.id, e.target.innerText);
                }
            }
        });

        // Load cached edits on startup
        window.onload = function() {
            document.querySelectorAll('.edit-field').forEach(el => {
                if (el.id) {
                    const saved = localStorage.getItem('c2c_edit_' + el.id);
                    if (saved) {
                        el.innerText = saved;
                    }
                }
            });
            initCounter();
            calculateQuote();
        };
    </script>
</body>
</html>
