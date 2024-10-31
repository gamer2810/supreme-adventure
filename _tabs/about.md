---
# the default layout is 'page'
icon: fas fa-info-circle
order: 4
---

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Resume Template</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .header, .section-title {
            text-align: center;
            font-weight: bold;
        }
        .section {
            margin-top: 20px;
        }
        .experience-item {
            margin-bottom: 10px;
        }
    </style>
</head>
<body>

    <div class="header">
        <p>Minh Kha Tran</p>
        <p>Macomb • Illinois, 61455 • khatranminh98us@gmail.com • (309)-259-0915</p>
    </div>

    <div class="section">
        <div class="section-title">Education</div>
        <p><strong>Western Illinois University</strong><br>
        Macomb, IL<br>
        Master of Science, Computer Science. <span style="text-align: right;">Expected Graduation Date 2026</span><br>

        <p><strong>University of Science - VNUHCM</strong><br>
        Ho Chi Minh, Viet Nam<br>
        Bachelor of Science, Computer Science. 3.38 <span style="text-align: right;">Graduated 2020</span><br>
    </div>

    <div class="section">
        <div class="section-title">Experience</div>

        <div class="experience-item">
            <p><strong>NAVER VIETNAM</strong><br>
            Ho Chi Minh, Viet Nam<br>
            Backend Software Engineer <span style="text-align: right;">Sep 2023 - Jun 2024</span></p>
            <ul>
                <li>Project: Phoning (<a href="https://play.google.com/store/apps/details?id=co.weverse.phoning&pcampaignid=web_share">Play Store link</a>)</li>
                <li>Developed and delivered a social platform for Korean idols (NewJeans) and their fans, utilizing a Spring Boot backend to support a user base of approximately 50K monthly active users.</li>
                <li>Acted as the main POC for two key features:
                    <ul>
                    <li>Calendar: Enabled idols to create events and interact with fan comments.</li>
                    <li>Podcast: Developed podcast management capabilities, integrating with streaming platforms for secure storage and distribution of podcast streams.</li>
                    </ul>
                </li>
                <li>Tackled technical challenges, including handling high sporadic read/write loads (10K reads/s, 1K writes/s) and implementing robust security measures to prevent unauthorized server access.</li>
                <li>Set up a secure production deployment environment using an in-house Kubernetes-based system, successfully passing NAVER’s company security review and meeting strict compliance standards.</li>
                <li>Conducted benchmarking and stress tests, achieving an average latency of under 100ms and no timeout under constant heavy load conditions (15,000 concurrent users repeatedly stressing 20 instances).</li>
                <li>Collaborated closely with Korean software developers and management, meeting all feature launch timelines (3 months for each feature) through coordinated efforts.</li>
            </ul>
        </div>

        <div class="experience-item">
            <p><strong>MoMo (M_Service)</strong><br>
            Ho Chi Minh, Viet Nam<br>
            Backend Software Engineer <span style="text-align: right;">Apr 2022 - Aug 2023</span></p>
            <ul>
            <li>Engineered and optimized a group of over 10 microservices, deployed on Google Kubernetes Engine, within a complex ecosystem of hundreds of services. These services were designed to:
                <ul>
                <li>Efficiently serve 1000 requests per second (RPS) for recommended advertisements with an average response time of 100 milliseconds to mobile applications through HTTP requests via Vert.X.</li>
                <li>Implemented a multi-tier caching strategy, combining local Caffeine cache and Redis, to reduce response times from 1.2 seconds to 100 milliseconds, saving thousands of dollars monthly in data query costs.</li>
                <li>Facilitate seamless inter-service communication through gRPC and ensure real-time data processing with Kafka.</li>
                <li>Provide a user-friendly platform for non-technical users to configure and manage ad campaigns.</li>
                <li>Gather and refine mobile application metrics, storing the valuable insights in BigQuery for data-driven ad optimization.</li>
                </ul>
            </li>
            </ul>
        </div>
    </div>

    <!-- <div class="section">
        <div class="section-title">Skills & Interests [Note: Optional]</div>
        <ul>
            <li><strong>Technical:</strong> List computer software and programming languages and your level of fluency.</li>
            <li><strong>Language:</strong> List foreign languages and your level of fluency.</li>
            <li><strong>Laboratory:</strong> List scientific / research lab techniques or tools [If Applicable].</li>
            <li><strong>Interests:</strong> List activities you enjoy that may spark interview conversation.</li>
        </ul>
    </div> -->

</body>