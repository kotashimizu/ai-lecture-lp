<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>セラピスト向けAI個別レクチャー | ICHI</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Hiragino Sans', 'Hiragino Kaku Gothic ProN', 'Yu Gothic', sans-serif;
            line-height: 1.7;
            color: #333;
            background-color: #f5f5f5;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 40px;
        }

        /* Header */
        header {
            background: white;
            padding: 30px 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .logo {
            font-size: 48px;
            font-weight: bold;
            color: #1A2B4C;
            text-align: center;
            letter-spacing: 8px;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #1A2B4C 0%, #2C3E50 100%);
            color: white;
            padding: 100px 0;
            text-align: center;
        }

        .hero h1 {
            font-size: clamp(1.8rem, 4vw, 2.8rem);
            margin-bottom: 30px;
            line-height: 1.5;
            font-weight: bold;
            max-width: 900px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero .subtitle {
            font-size: clamp(1rem, 2.5vw, 1.3rem);
            margin-bottom: 50px;
            opacity: 0.9;
            line-height: 1.7;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-button {
            display: inline-block;
            background: #00A99D;
            color: white;
            padding: 20px 40px;
            font-size: 1.2rem;
            font-weight: bold;
            text-decoration: none;
            border-radius: 8px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 169, 157, 0.3);
        }

        .cta-button:hover {
            background: #008B82;
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(0, 169, 157, 0.4);
        }

        /* Section Styles */
        .section {
            padding: 80px 0;
            background: white;
            margin: 60px 0;
        }

        .section-title {
            font-size: clamp(1.8rem, 3.5vw, 2.4rem);
            text-align: center;
            margin-bottom: 60px;
            color: #1A2B4C;
            position: relative;
            padding-bottom: 20px;
            line-height: 1.4;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background: #00A99D;
        }

        /* Problems Section */
        .problems-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .problem-item {
            background: #f8f9fa;
            padding: 30px;
            border-left: 4px solid #00A99D;
            border-radius: 8px;
            font-size: 1.1rem;
            line-height: 1.6;
        }

        .problem-item::before {
            content: '✓';
            color: #00A99D;
            font-weight: bold;
            margin-right: 12px;
            font-size: 1.2rem;
        }

        .problems-conclusion {
            text-align: center;
            font-size: clamp(1.1rem, 2.5vw, 1.4rem);
            font-weight: bold;
            color: #1A2B4C;
            max-width: 600px;
            margin: 0 auto;
            line-height: 1.5;
        }

        /* Solutions Section */
        .solutions {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
        }

        .solution-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(360px, 1fr));
            gap: 40px;
        }

        .solution-card {
            background: white;
            padding: 40px;
            border-radius: 12px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .solution-card:hover {
            transform: translateY(-5px);
        }

        .solution-card h3 {
            color: #1A2B4C;
            margin-bottom: 20px;
            font-size: clamp(1.2rem, 2.5vw, 1.6rem);
            line-height: 1.4;
        }

        .solution-card .highlight {
            color: #00A99D;
            font-weight: bold;
            font-size: clamp(1rem, 2vw, 1.2rem);
            margin-bottom: 15px;
            line-height: 1.5;
        }

        .solution-card p {
            font-size: 1rem;
            line-height: 1.6;
        }

        /* Reasons Section */
        .reasons {
            background: #1A2B4C;
            color: white;
        }

        .reasons .section-title {
            color: white;
        }

        .reasons .section-title::after {
            background: #00A99D;
        }

        .reason-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
        }

        .reason-card {
            background: rgba(255,255,255,0.1);
            padding: 40px;
            border-radius: 12px;
            backdrop-filter: blur(10px);
        }

        .reason-number {
            background: #00A99D;
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-bottom: 25px;
            font-size: 1.5rem;
        }

        .reason-card h3 {
            font-size: clamp(1.2rem, 2.5vw, 1.5rem);
            margin-bottom: 20px;
            line-height: 1.4;
        }

        .reason-card .reason-subtitle {
            color: #00A99D;
            font-weight: bold;
            font-size: clamp(1rem, 2vw, 1.2rem);
            margin-bottom: 20px;
            line-height: 1.5;
        }

        .reason-card ul {
            margin-left: 0;
            padding-left: 0;
            list-style: none;
        }

        .reason-card ul li {
            margin-bottom: 12px;
            padding-left: 25px;
            position: relative;
            line-height: 1.6;
        }

        .reason-card ul li::before {
            content: '•';
            color: #00A99D;
            position: absolute;
            left: 0;
            font-weight: bold;
            font-size: 1.2rem;
        }

        /* Testimonials */
        .testimonials {
            background: linear-gradient(135deg, #00A99D 0%, #008B82 100%);
            color: white;
        }

        .testimonials .section-title {
            color: white;
        }

        .testimonials .section-title::after {
            background: white;
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
            margin-bottom: 50px;
        }

        .testimonial-card {
            background: rgba(255,255,255,0.15);
            padding: 35px;
            border-radius: 12px;
            backdrop-filter: blur(10px);
        }

        .testimonial-name {
            font-weight: bold;
            margin-bottom: 15px;
            color: #F5F7FA;
            font-size: 1.1rem;
        }

        .testimonial-card p {
            line-height: 1.7;
            font-size: 1rem;
        }

        .satisfaction {
            text-align: center;
            font-size: clamp(1.1rem, 2.5vw, 1.4rem);
            font-weight: bold;
            padding: 30px;
            background: rgba(255,255,255,0.2);
            border-radius: 12px;
            backdrop-filter: blur(10px);
        }

        /* Content & Price */
        .content-section {
            background: #f8f9fa;
        }

        .content-grid {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 60px;
            align-items: start;
        }

        .lecture-content {
            background: white;
            padding: 50px;
            border-radius: 12px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
        }

        .lecture-content > h3 {
            color: #1A2B4C;
            margin-bottom: 40px;
            font-size: clamp(1.3rem, 2.5vw, 1.7rem);
            line-height: 1.3;
        }

        .content-item {
            margin-bottom: 35px;
            padding: 25px;
            border-left: 4px solid #00A99D;
            background: #f8f9fa;
            border-radius: 0 8px 8px 0;
        }

        .content-item h4 {
            color: #1A2B4C;
            margin-bottom: 15px;
            font-size: clamp(1.1rem, 2vw, 1.3rem);
            line-height: 1.3;
        }

        .content-item ul {
            margin-left: 0;
            padding-left: 0;
            list-style: none;
        }

        .content-item ul li {
            margin-bottom: 8px;
            padding-left: 20px;
            position: relative;
            line-height: 1.6;
        }

        .content-item ul li::before {
            content: '•';
            color: #00A99D;
            position: absolute;
            left: 0;
            font-weight: bold;
        }

        .benefits-section h3 {
            color: #1A2B4C;
            margin: 50px 0 25px 0;
            font-size: clamp(1.3rem, 2.5vw, 1.7rem);
            line-height: 1.3;
        }

        .benefits-list {
            margin-left: 0;
            padding-left: 0;
            list-style: none;
        }

        .benefits-list li {
            margin-bottom: 15px;
            padding-left: 25px;
            position: relative;
            line-height: 1.6;
            font-size: 1.05rem;
        }

        .benefits-list li::before {
            content: '✓';
            color: #00A99D;
            position: absolute;
            left: 0;
            font-weight: bold;
            font-size: 1.1rem;
        }

        .benefits-list strong {
            color: #1A2B4C;
        }

        .price-card {
            background: #1A2B4C;
            color: white;
            padding: 50px 35px;
            border-radius: 12px;
            text-align: center;
            position: sticky;
            top: 20px;
            height: fit-content;
        }

        .limited {
            background: #00A99D;
            color: white;
            padding: 12px 25px;
            border-radius: 25px;
            font-size: 0.95rem;
            margin-bottom: 25px;
            display: inline-block;
            font-weight: bold;
        }

        .original-price {
            text-decoration: line-through;
            opacity: 0.7;
            font-size: 1.3rem;
            margin-bottom: 10px;
        }

        .special-price {
            font-size: clamp(2rem, 4vw, 2.8rem);
            font-weight: bold;
            color: #00A99D;
            margin: 20px 0 30px 0;
            line-height: 1.2;
        }

        .price-card .cta-button {
            width: 100%;
            margin-top: 25px;
            padding: 18px 20px;
            font-size: 1.1rem;
        }

        /* FAQ */
        .faq-item {
            background: white;
            margin-bottom: 25px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            overflow: hidden;
        }

        .faq-question {
            background: #1A2B4C;
            color: white;
            padding: 25px 30px;
            font-weight: bold;
            cursor: pointer;
            font-size: clamp(1rem, 2vw, 1.1rem);
            line-height: 1.4;
        }

        .faq-answer {
            padding: 25px 30px;
            background: white;
            line-height: 1.7;
            font-size: 1rem;
        }

        /* Profile */
        .profile {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
        }

        .profile-content {
            text-align: center;
            background: white;
            padding: 50px;
            border-radius: 12px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.1);
        }

        .profile-name {
            font-size: clamp(1.8rem, 3vw, 2.2rem);
            color: #1A2B4C;
            margin-bottom: 30px;
            line-height: 1.3;
        }

        .profile-list {
            text-align: left;
            max-width: 600px;
            margin: 0 auto;
            list-style: none;
            padding-left: 0;
        }

        .profile-list li {
            margin-bottom: 15px;
            padding-left: 30px;
            position: relative;
            line-height: 1.6;
            font-size: 1.05rem;
        }

        .profile-list li::before {
            content: '•';
            color: #00A99D;
            position: absolute;
            left: 0;
            font-weight: bold;
            font-size: 1.2rem;
        }

        /* Final CTA */
        .final-cta {
            background: linear-gradient(135deg, #1A2B4C 0%, #2C3E50 100%);
            color: white;
            text-align: center;
            padding: 100px 0;
        }

        .final-cta h2 {
            font-size: clamp(1.8rem, 3.5vw, 2.4rem);
            margin-bottom: 35px;
            line-height: 1.3;
        }

        .final-cta .price-highlight {
            font-size: clamp(2rem, 4vw, 2.8rem);
            color: #00A99D;
            font-weight: bold;
            margin: 25px 0;
            line-height: 1.2;
        }

        .final-cta .description {
            font-size: clamp(1.1rem, 2.5vw, 1.4rem);
            margin: 40px auto;
            max-width: 700px;
            line-height: 1.6;
        }

        .final-cta .cta-button {
            font-size: 1.4rem;
            padding: 25px 50px;
            margin-top: 20px;
        }

        .final-cta .notes {
            margin-top: 50px;
            font-size: 0.95rem;
            opacity: 0.8;
            line-height: 1.8;
        }

        .final-cta .notes p {
            margin-bottom: 8px;
        }

        /* Footer Message */
        .footer-message {
            background: #f8f9fa;
            padding: 80px 0;
            text-align: center;
        }

        .footer-message h3 {
            color: #1A2B4C;
            margin-bottom: 40px;
            font-size: clamp(1.5rem, 3vw, 2rem);
            line-height: 1.3;
        }

        .footer-message .message-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .footer-message p {
            font-size: clamp(1rem, 2vw, 1.2rem);
            line-height: 1.8;
            margin-bottom: 25px;
        }

        .footer-message .cta-button {
            margin-top: 30px;
        }

        /* Responsive Design */
        @media (max-width: 1024px) {
            .content-grid {
                grid-template-columns: 1fr;
                gap: 40px;
            }

            .price-card {
                position: static;
                order: -1;
            }
        }

        @media (max-width: 768px) {
            .container {
                padding: 0 20px;
            }

            .hero {
                padding: 60px 0;
            }

            .section {
                padding: 60px 0;
                margin: 40px 0;
            }

            .section-title {
                margin-bottom: 40px;
            }

            .solution-cards,
            .reason-grid,
            .testimonial-grid {
                grid-template-columns: 1fr;
                gap: 30px;
            }

            .problems-list {
                grid-template-columns: 1fr;
                gap: 20px;
            }

            .lecture-content {
                padding: 30px 25px;
            }

            .price-card {
                padding: 35px 25px;
            }

            .final-cta {
                padding: 60px 0;
            }

            .footer-message {
                padding: 60px 0;
            }

            .logo {
                font-size: 36px;
                letter-spacing: 6px;
            }
        }

        @media (max-width: 480px) {
            .container {
                padding: 0 15px;
            }

            .cta-button {
                padding: 18px 30px;
                font-size: 1.1rem;
            }

            .final-cta .cta-button {
                padding: 20px 35px;
                font-size: 1.2rem;
            }

            .content-item,
            .solution-card,
            .reason-card,
            .testimonial-card {
                padding: 25px 20px;
            }

            .faq-question,
            .faq-answer {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="logo">ICHI.</div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>「何をしたいのか？」<br>「何に困っているのか？」<br>あなたの課題を90分で<br>AIソリューションに変える個別レクチャー</h1>
            <p class="subtitle">AIを使うことが目的ではありません。<br>あなたの「やりたいこと」「困りごと」にフォーカスし、<br>AIをツールとしてどう活用するかを1対1で実践します</p>
            <a href="#apply" class="cta-button">今すぐ申込む</a>
        </div>
    </section>

    <!-- Problems Section -->
    <section class="section">
        <div class="container">
            <h2 class="section-title">こんなお悩み、ありませんか？</h2>
            <div class="problems-list">
                <div class="problem-item">毎日のセッション記録に時間がかかりすぎる</div>
                <div class="problem-item">移動時間を有効活用したいが方法がわからない</div>
                <div class="problem-item">AIに興味はあるが、具体的に何から始めればいいかわからない</div>
                <div class="problem-item">論文検索や情報収集に時間を取られている</div>
                <div class="problem-item">同業他社に差をつけたいが、デジタル化が進まない</div>
            </div>
            <p class="problems-conclusion">
                大切なのは「AIを覚えること」ではなく<br>「あなたの課題を解決すること」です。
            </p>
        </div>
    </section>

    <!-- Solutions Section -->
    <section class="section solutions">
        <div class="container">
            <h2 class="section-title">なぜ90分の個別レクチャーで<br>業務が激変するのか？</h2>
            <div class="solution-cards">
                <div class="solution-card">
                    <h3>課題解決にフォーカスしたアプローチ</h3>
                    <div class="highlight">「何をしたいのか？」「何に困っているのか？」という<br>受講者の課題を徹底的にヒアリング</div>
                    <p>それをどのようにAIで解決するのかを<br>提案・実践する時間にしています</p>
                </div>
                <div class="solution-card">
                    <h3>AIはツール、使いこなし方が重要</h3>
                    <div class="highlight">AIを使うことが目的ではなく、<br>業務課題を解決する手段としてのAI活用法を習得</div>
                    <p>いつ・どのタイミングで何を使うのか？<br>という実践的な判断力を身につけます</p>
                </div>
                <div class="solution-card">
                    <h3>完全個別の課題解決設計</h3>
                    <div class="highlight">8名のセラピスト・医療従事者への<br>個別レクチャー実績から</div>
                    <p>あなた独自の「やりたいこと」「困りごと」に<br>特化したソリューションをカスタマイズ提供</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Reasons Section -->
    <section class="section reasons">
        <div class="container">
            <h2 class="section-title">3つの理由で選ばれています</h2>
            <div class="reason-grid">
                <div class="reason-card">
                    <div class="reason-number">1</div>
                    <h3>課題解決重視のアプローチ</h3>
                    <p class="reason-subtitle">「AIを学ぶ」のではなく<br>「課題を解決する」ことが目的</p>
                    <ul>
                        <li>あなたの「やりたいこと」「困りごと」を明確化</li>
                        <li>最適なAIツールの選択と<br>タイミングを提案</li>
                        <li>課題解決までの具体的な<br>ロードマップを設計</li>
                    </ul>
                </div>
                <div class="reason-card">
                    <div class="reason-number">2</div>
                    <h3>ツールとしてのAI活用術</h3>
                    <p class="reason-subtitle">AIはあくまでもツール。<br>どう使いこなすかが重要</p>
                    <ul>
                        <li>いつ・どのタイミングで<br>何のAIを使うかの判断基準</li>
                        <li>複数のAIツールの使い分け方法</li>
                        <li>業務フローの中での<br>AI組み込み戦略</li>
                    </ul>
                </div>
                <div class="reason-card">
                    <div class="reason-number">3</div>
                    <h3>継続サポート体制</h3>
                    <p class="reason-subtitle">レクチャー後もフォロー</p>
                    <ul>
                        <li>アーカイブ動画で何度でも復習</li>
                        <li>専用コミュニティで<br>質問・情報交換</li>
                        <li>1ヶ月ロードマップの提案</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <section class="section testimonials">
        <div class="container">
            <h2 class="section-title">参加者の成果をご紹介</h2>
            <div class="testimonial-grid">
                <div class="testimonial-card">
                    <div class="testimonial-name">須田さん（メディカルフィットネス経営）</div>
                    <p>「セッション後の記録作成が、移動中の音声入力で完結するようになりました。<br>1日30分の時短効果で、月15時間を他業務に充てることができています」</p>
                </div>
                <div class="testimonial-card">
                    <div class="testimonial-name">山崎さん（訪問看護師）</div>
                    <p>「業務効率化のアプリ開発に挑戦。<br>GASを使って簡単な管理ツールを作成でき、<br>チーム全体の生産性が向上しました」</p>
                </div>
                <div class="testimonial-card">
                    <div class="testimonial-name">宮下さん（訪問看護師）</div>
                    <p>「AI活用で自分のやりたい事業展開の具体的な道筋が見えました。<br>ホームページ作成からマーケティングまで、<br>一人でできることが大幅に増えました」</p>
                </div>
            </div>
            <div class="satisfaction">参加者満足度：100%（9名中9名が満足と回答）</div>
        </div>
    </section>

    <!-- Content & Price -->
    <section class="section content-section">
        <div class="container">
            <h2 class="section-title">レクチャー内容・特典</h2>
            <div class="content-grid">
                <div class="lecture-content">
                    <h3>基本レクチャー（60-90分）</h3>
                    
                    <div class="content-item">
                        <h4>1. 課題の明確化（15分）</h4>
                        <ul>
                            <li>「何をしたいのか？」「何に困っているのか？」の深堀り</li>
                            <li>現在の業務フローと<br>非効率ポイントの特定</li>
                            <li>理想的な状態の具体化</li>
                        </ul>
                    </div>

                    <div class="content-item">
                        <h4>2. AIソリューション設計（30分）</h4>
                        <ul>
                            <li>あなたの課題をどのようにAIで<br>解決するかの提案</li>
                            <li>最適なツール選択と<br>使用タイミングの実演</li>
                            <li>実際の作業での活用デモと実践</li>
                        </ul>
                    </div>

                    <div class="content-item">
                        <h4>3. 実装・活用戦略（30分）</h4>
                        <ul>
                            <li>業務フローの中での<br>AI組み込み方法</li>
                            <li>いつ・どのタイミングで<br>何を使うかの判断基準</li>
                            <li>継続的な改善・発展の可能性</li>
                        </ul>
                    </div>

                    <div class="content-item">
                        <h4>4. 次ステップの具体化（15分）</h4>
                        <ul>
                            <li>あなた専用の1ヶ月実践<br>ロードマップ</li>
                            <li>課題解決後の新たな<br>可能性の提示</li>
                        </ul>
                    </div>

                    <div class="benefits-section">
                        <h3>特典</h3>
                        <ul class="benefits-list">
                            <li><strong>レクチャー動画アーカイブ</strong>：<br>録画データで何度でも復習</li>
                            <li><strong>コミュニティ参加権</strong>：<br>継続的な質問・情報交換が可能</li>
                            <li><strong>個別カスタマイズ資料</strong>：<br>あなたの業務特化の活用例集</li>
                        </ul>
                    </div>
                </div>

                <div class="price-card">
                    <div class="limited">限定10名まで</div>
                    <div class="original-price">通常価格：30,000円</div>
                    <div style="font-size: 1.2rem; margin-bottom: 10px;">↓</div>
                    <div style="color: #00A99D; font-weight: bold; font-size: 1.1rem;">早期申込特価</div>
                    <div class="special-price">19,800円</div>
                    <a href="#apply" class="cta-button">今すぐ申込む</a>
                </div>
            </div>
        </div>
    </section>

    <!-- FAQ -->
    <section class="section">
        <div class="container">
            <h2 class="section-title">よくあるご質問</h2>
            
            <div class="faq-item">
                <div class="faq-question">Q: AIの知識が全くないのですが大丈夫ですか？</div>
                <div class="faq-answer">A: はい、大丈夫です。このレクチャーは「AIを覚える」ことが目的ではなく<br>「あなたの課題を解決する」ことが目的です。AI知識は必要ありません。</div>
            </div>

            <div class="faq-item">
                <div class="faq-question">Q: レクチャー後のフォローはありますか？</div>
                <div class="faq-answer">A: アーカイブ動画とコミュニティ参加権により、<br>継続的なサポートを提供します。</div>
            </div>

            <div class="faq-item">
                <div class="faq-question">Q: アプリ開発は必須ですか？</div>
                <div class="faq-answer">A: 必須ではありません。まずは日常業務の効率化からスタートし、<br>興味がある方にはアプリ開発の可能性もご紹介します。</div>
            </div>

            <div class="faq-item">
                <div class="faq-question">Q: オンライン受講は可能ですか？</div>
                <div class="faq-answer">A: はい、Zoom等のオンラインツールで実施いたします。<br>全国どこからでも受講可能です。</div>
            </div>

            <div class="faq-item">
                <div class="faq-question">Q: 返金保証はありますか？</div>
                <div class="faq-answer">A: レクチャー内容にご満足いただけない場合、<br>全額返金いたします。</div>
            </div>
        </div>
    </section>

    <!-- Profile -->
    <section class="section profile">
        <div class="container">
            <h2 class="section-title">講師プロフィール</h2>
            <div class="profile-content">
                <div class="profile-name">志水康太</div>
                <ul class="profile-list">
                    <li>非エンジニアから<br>AI活用・アプリ開発に転身</li>
                    <li>医療・療養業界向け<br>AI活用コンサルタント</li>
                    <li>これまで50名以上の医療従事者に<br>AI活用をレクチャー</li>
                    <li>自身も複数のアプリ開発・運用実績</li>
                </ul>
            </div>
        </div>
    </section>

    <!-- Final CTA -->
    <section class="final-cta" id="apply">
        <div class="container">
            <h2>今すぐお申込みください</h2>
            <div class="limited">限定10名・早期申込特価</div>
            <div class="price-highlight">19,800円<span style="font-size: 1.4rem; opacity: 0.8;">（通常30,000円）</span></div>
            <p class="description">業務効率化で手に入れた時間で、<br>本当にやりたい仕事に集中しませんか？</p>
            <a href="#" class="cta-button">お申込みはこちら</a>
            
            <div class="notes">
                <p>※お申込み後、事前アンケートをお送りいたします</p>
                <p>※レクチャー日程は個別に調整いたします</p>
                <p>※定員に達し次第、受付終了となります</p>
            </div>
        </div>
    </section>

    <!-- Footer Message -->
    <section class="footer-message">
        <div class="container">
            <h3>追伸</h3>
            <div class="message-content">
                <p>AI活用は「難しそう」「時間がない」という理由で後回しにしがちですが、<br>実際に始めてみると「もっと早くやっておけばよかった」と<br>感じる方がほとんどです。</p>
                <p>この機会を逃すと、業務効率化のチャンスも逃してしまいます。<br>今すぐ行動を起こして、理想的な働き方を手に入れてください。</p>
                <a href="#apply" class="cta-button">今すぐ申込む</a>
            </div>
        </div>
    </section>
</body>
</html>