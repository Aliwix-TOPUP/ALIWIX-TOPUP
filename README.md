<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ALIWIX - Recharge Jeux Mobile & Services</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', 'Arial', sans-serif;
            background: linear-gradient(135deg, #0a1a0f 0%, #0d2413 100%);
            min-height: 100vh;
            color: white;
        }

        .page {
            display: none;
            min-height: 100vh;
            padding: 30px 20px;
        }

        .page.active {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        /* Logo */
        .logo-container {
            margin-bottom: 40px;
            text-align: center;
        }

        .logo-img {
            max-width: 220px;
            height: auto;
            border-radius: 20px;
            box-shadow: 0 0 30px rgba(37, 211, 102, 0.4);
            border: 2px solid rgba(37, 211, 102, 0.5);
        }

        .content {
            max-width: 500px;
            width: 100%;
            text-align: center;
            background: rgba(0, 0, 0, 0.4);
            backdrop-filter: blur(10px);
            padding: 50px 30px;
            border-radius: 30px;
            border: 1px solid rgba(37, 211, 102, 0.3);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.6);
        }

        .wave {
            font-size: 4rem;
            display: block;
            margin-bottom: 20px;
            animation: wave 2s infinite;
        }

        @keyframes wave {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(15deg); }
            75% { transform: rotate(-10deg); }
        }

        h1 {
            font-size: 2.2rem;
            margin-bottom: 15px;
            background: linear-gradient(45deg, #4EFF8B, #FFD700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        h2 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #4EFF8B, #FFD700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        p {
            font-size: 1.1rem;
            line-height: 1.6;
            margin-bottom: 30px;
            color: #c0eec0;
        }

        .btn {
            display: inline-block;
            background: linear-gradient(45deg, #25D366, #1a8a44);
            color: white;
            padding: 16px 40px;
            font-size: 1.3rem;
            font-weight: bold;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            text-decoration: none;
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(37, 211, 102, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(37, 211, 102, 0.5);
            background: linear-gradient(45deg, #20c058, #0e8a3a);
        }

        .construction-icon {
            font-size: 4rem;
            margin-bottom: 20px;
        }

        .contact-rapide {
            margin-top: 30px;
            padding-top: 20px;
            border-top: 1px solid rgba(37, 211, 102, 0.4);
        }

        .contact-rapide a {
            color: #4EFF8B;
            text-decoration: none;
            font-size: 1.2rem;
            font-weight: bold;
        }

        .whatsapp-number {
            background: rgba(37, 211, 102, 0.2);
            padding: 8px 15px;
            border-radius: 30px;
            display: inline-block;
            margin-top: 5px;
            border: 1px solid rgba(37, 211, 102, 0.4);
        }

        /* Galerie */
        .galerie {
            max-width: 1100px;
            width: 100%;
            padding: 20px;
        }

        .produits-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            justify-content: center;
            align-items: stretch;
        }

        .produit-card {
            background: rgba(0, 0, 0, 0.4);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 25px 20px 20px 20px;
            border: 1px solid rgba(37, 211, 102, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .produit-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.7);
            border-color: rgba(37, 211, 102, 0.7);
            box-shadow: 0 10px 30px rgba(37, 211, 102, 0.2);
        }

        .produit-image {
            width: 140px;
            height: 140px;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .produit-image img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.4);
        }

        .produit-nom {
            font-size: 1.4rem;
            font-weight: bold;
            margin-bottom: 8px;
            color: #4EFF8B;
        }

        .produit-pack {
            font-size: 1rem;
            color: #a0d8a0;
            margin-bottom: 25px;
        }

        .btn-achat {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            background: linear-gradient(45deg, #25D366, #128C7E);
            color: white;
            padding: 12px 25px;
            font-size: 1.1rem;
            font-weight: bold;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            text-decoration: none;
            transition: all 0.3s ease;
            width: 100%;
            box-shadow: 0 5px 15px rgba(37, 211, 102, 0.4);
        }

        .btn-achat:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(37, 211, 102, 0.7);
            background: linear-gradient(45deg, #20c058, #0e7365);
        }

        .btn-retour {
            background: transparent;
            color: #4EFF8B;
            border: 2px solid #25D366;
            box-shadow: none;
            margin-top: 30px;
            padding: 12px 30px;
            font-size: 1rem;
        }

        .btn-retour:hover {
            background: rgba(37, 211, 102, 0.15);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(37, 211, 102, 0.3);
        }

        .sous-titre {
            color: #7ed87e;
        }

        /* Titre ALIWIX textuel pour pages 2 et 3 */
        .aliwix-titre {
            font-size: 2.5rem;
            font-weight: bold;
            margin-bottom: 30px;
            background: linear-gradient(45deg, #4EFF8B, #FFD700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 20px rgba(37, 211, 102, 0.3);
        }

        @media (max-width: 600px) {
            .logo-img {
                max-width: 180px;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .content {
                padding: 40px 20px;
            }
            
            .produits-grid {
                grid-template-columns: 1fr;
            }

            .aliwix-titre {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>

    <!-- ============================================= -->
    <!-- PAGE 1 : ACCUEIL CHALEUREUX (AVEC LOGO)        -->
    <!-- ============================================= -->
    <div id="page1" class="page active">
        <div class="logo-container">
            <img src="https://i.ibb.co/JWGz6qvf/IMG-20260418-WA0038.jpg" alt="ALIWIX" class="logo-img">
        </div>
        
        <div class="content">
            <span class="wave">👋</span>
            <h1>Salut ! Et Bienvenue</h1>
            <p>sur notre site vitrine</p>
            <p class="sous-titre" style="font-size: 0.9rem; margin-top: -10px;">Recharge • Streaming • Crypto • Gift Cards</p>
            
            <button class="btn" onclick="goToPage(2)">SUIVANT →</button>
        </div>
    </div>

    <!-- ============================================= -->
    <!-- PAGE 2 : MESSAGE D'ATTENTE (SANS LOGO)         -->
    <!-- ============================================= -->
    <div id="page2" class="page">
        <div class="content">
            <div class="aliwix-titre">ALIWIX</div>
            <div class="construction-icon">🛠️👷</div>
            <h2>La boutique e-commerce arrive bientôt !</h2>
            <p>Notre site de commande automatique est en construction. En attendant, commande directement via WhatsApp en quelques clics.</p>
            
            <button class="btn" onclick="goToPage(3)">📲 VOIR LES OFFRES DISPONIBLES →</button>
            
            <div class="contact-rapide">
                <p style="margin-bottom: 10px; font-size: 0.95rem; color: #a0d8a0;">Ou contacte-nous directement :</p>
                <a href="https://wa.me/50944164712" target="_blank" class="whatsapp-number">
                    💬 +509 44 16 4712
                </a>
            </div>
            
            <button class="btn-retour" onclick="goToPage(1)">← Retour à l'accueil</button>
        </div>
    </div>

    <!-- ============================================= -->
    <!-- PAGE 3 : GALERIE 6 PRODUITS (SANS LOGO)        -->
    <!-- ============================================= -->
    <div id="page3" class="page">
        <div class="galerie">
            <div class="aliwix-titre" style="text-align: center;">ALIWIX</div>
            <h2 style="text-align: center;">✨ Nos Services disponibles ✨</h2>
            
            <div class="produits-grid">
                
                <!-- PRODUIT 1 : FREE FIRE -->
                <div class="produit-card">
                    <div class="produit-image">
                        <img src="https://i.ibb.co/m546G7S8/images-2.png" alt="Free Fire">
                    </div>
                    <div class="produit-nom">Free Fire</div>
                    <div class="produit-pack">Diamants & Pass</div>
                    <a href="https://wa.me/50944164712?text=Bonjour%20ALIWIX%20!%20Je%20suis%20int%C3%A9ress%C3%A9%20par%20*Free%20Fire*%20(Diamants%20ou%20Pass).%20Pouvez-vous%20m'aider%20%3F" 
                       target="_blank" class="btn-achat">
                        🛒 Commander
                    </a>
                </div>

                <!-- PRODUIT 2 : NETFLIX -->
                <div class="produit-card">
                    <div class="produit-image">
                        <img src="https://i.ibb.co/MkGR6Vh2/t-l-chargement-1.png" alt="Netflix">
                    </div>
                    <div class="produit-nom">Netflix</div>
                    <div class="produit-pack">Abonnement & Recharge</div>
                    <a href="https://wa.me/50944164712?text=Bonjour%20ALIWIX%20!%20Je%20suis%20int%C3%A9ress%C3%A9%20par%20*Netflix*%20(Abonnement%20ou%20Recharge).%20Pouvez-vous%20m'aider%20%3F" 
                       target="_blank" class="btn-achat">
                        🛒 Commander
                    </a>
                </div>

                <!-- PRODUIT 3 : CRYPTOMONNAIES -->
                <div class="produit-card">
                    <div class="produit-image">
                        <img src="https://i.ibb.co/qFkH5hFc/images-2.jpg" alt="Cryptomonnaies">
                    </div>
                    <div class="produit-nom">Cryptomonnaies</div>
                    <div class="produit-pack">Achat / Vente / Échange</div>
                    <a href="https://wa.me/50944164712?text=Bonjour%20ALIWIX%20!%20Je%20suis%20int%C3%A9ress%C3%A9%20par%20*Cryptomonnaies*%20(Achat%2C%20Vente%20ou%20%C3%89change).%20Pouvez-vous%20m'aider%20%3F" 
                       target="_blank" class="btn-achat">
                        🛒 Commander
                    </a>
                </div>

                <!-- PRODUIT 4 : GIFT CARD -->
                <div class="produit-card">
                    <div class="produit-image">
                        <img src="https://i.ibb.co/ZpwyyKX9/images-8.jpg" alt="Gift Card">
                    </div>
                    <div class="produit-nom">Gift Card</div>
                    <div class="produit-pack">Toutes plateformes</div>
                    <a href="https://wa.me/50944164712?text=Bonjour%20ALIWIX%20!%20Je%20suis%20int%C3%A9ress%C3%A9%20par%20*Gift%20Card*.%20Pouvez-vous%20m'aider%20%3F" 
                       target="_blank" class="btn-achat">
                        🛒 Commander
                    </a>
                </div>

                <!-- PRODUIT 5 : DLS -->
                <div class="produit-card">
                    <div class="produit-image">
                        <img src="https://i.ibb.co/ZR57F77r/images-1.jpg" alt="Dream League Soccer">
                    </div>
                    <div class="produit-nom">Dream League Soccer</div>
                    <div class="produit-pack">Pièces & Ressources</div>
                    <a href="https://wa.me/50944164712?text=Bonjour%20ALIWIX%20!%20Je%20suis%20int%C3%A9ress%C3%A9%20par%20*Dream%20League%20Soccer*%20(Pi%C3%A8ces%20ou%20Ressources).%20Pouvez-vous%20m'aider%20%3F" 
                       target="_blank" class="btn-achat">
                        🛒 Commander
                    </a>
                </div>

                <!-- PRODUIT 6 : TIKTOK -->
                <div class="produit-card">
                    <div class="produit-image">
                        <img src="https://i.ibb.co/Jj16BcM2/t-l-chargement.png" alt="TikTok">
                    </div>
                    <div class="produit-nom">TikTok</div>
                    <div class="produit-pack">Pièces & Followers</div>
                    <a href="https://wa.me/50944164712?text=Bonjour%20ALIWIX%20!%20Je%20suis%20int%C3%A9ress%C3%A9%20par%20*TikTok*%20(Pi%C3%A8ces%20ou%20Followers).%20Pouvez-vous%20m'aider%20%3F" 
                       target="_blank" class="btn-achat">
                        🛒 Commander
                    </a>
                </div>

            </div>
            
            <div style="text-align: center; margin-top: 30px;">
                <button class="btn-retour" onclick="goToPage(2)">← Retour</button>
            </div>
        </div>
    </div>

    <script>
        function goToPage(pageNumber) {
            document.getElementById('page1').classList.remove('active');
            document.getElementById('page2').classList.remove('active');
            document.getElementById('page3').classList.remove('active');
            document.getElementById('page' + pageNumber).classList.add('active');
            window.scrollTo(0, 0);
        }
    </script>

</body>
</html>
