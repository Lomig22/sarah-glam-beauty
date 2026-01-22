# 🎨 Guide de Personnalisation - Sarah Glam Beauty

Ce guide vous aidera à personnaliser facilement votre site pour qu'il reflète parfaitement votre identité de marque.

## 📸 Ajouter Vos Photos

### Section Galerie

Remplacez les placeholders dans la section galerie (ligne ~230 dans `index.html`) :

**Actuellement :**
```html
<div class="galerie-item fade-in-up">
    <div class="galerie-placeholder">
        <span class="placeholder-icon">👁️</span>
        <p>Extensions de cils</p>
    </div>
</div>
```

**Après personnalisation :**
```html
<div class="galerie-item fade-in-up">
    <img src="images/extensions-cils.jpg" alt="Extensions de cils réalisées par Sarah Glam Beauty">
</div>
```

### Section Hero (Image de fond)

Ajoutez une image de fond dans le CSS (`styles.css` ligne ~145) :

```css
.hero {
    background: linear-gradient(rgba(10, 10, 10, 0.6), rgba(10, 10, 10, 0.6)),
                url('images/hero-background.jpg') center/cover no-repeat;
}
```

## 🎨 Changer les Couleurs

### Palette Principale

Modifiez les variables CSS dans `styles.css` (lignes 8-17) :

```css
:root {
    --noir-profond: #0a0a0a;      /* Noir principal */
    --dore-elegant: #d4af37;       /* Doré pour les accents */
    --violet-doux: #b8a0c8;        /* Violet pour les dégradés */
    --blanc: #ffffff;              /* Blanc pour le fond */
}
```

### Exemples de Palettes Alternatives

**Palette Rose Gold & Noir :**
```css
--noir-profond: #1a1a1a;
--dore-elegant: #E8C4B8;
--violet-doux: #D4A5A5;
```

**Palette Bleu & Or :**
```css
--noir-profond: #0f1c2e;
--dore-elegant: #d4af37;
--violet-doux: #8ba8c8;
```

## ✍️ Modifier les Textes

### Titre Principal (Hero)

Ligne 31 dans `index.html` :
```html
<h1 class="hero-title">Votre Nouveau Titre Ici</h1>
```

### Sous-titre

Ligne 32 dans `index.html` :
```html
<p class="hero-subtitle">Votre nouveau sous-titre descriptif</p>
```

### Promesse

Ligne 47 dans `index.html` :
```html
<p class="promesse-text">
    Votre texte de promesse personnalisé...
</p>
```

## 💄 Ajouter/Modifier des Prestations

### Ajouter une Nouvelle Prestation

Dans la section prestations (ligne ~130), dupliquez une carte existante :

```html
<div class="prestation-card fade-in-up">
    <div class="card-icon">💅</div>
    <h3 class="card-title">Nouvelle Prestation</h3>
    <div class="card-divider"></div>
    <ul class="services-list">
        <li>Service 1</li>
        <li>Service 2</li>
        <li>Service 3</li>
    </ul>
    <p class="card-description">
        Description de votre nouvelle prestation.
    </p>
</div>
```

### Modifier une Prestation Existante

Trouvez la carte correspondante et modifiez :
- L'icône : `<div class="card-icon">...</div>`
- Le titre : `<h3 class="card-title">...</h3>`
- Les services : `<li>...</li>`
- La description : `<p class="card-description">...</p>`

## 🔗 Configurer les Réseaux Sociaux

### Footer (ligne ~332)

Remplacez les `#` par vos liens réels :

```html
<div class="social-icons">
    <a href="https://instagram.com/votre-compte" aria-label="Instagram">📷</a>
    <a href="https://facebook.com/votre-page" aria-label="Facebook">👤</a>
    <a href="https://pinterest.com/votre-compte" aria-label="Pinterest">📌</a>
</div>
```

## 📧 Connecter le Formulaire

### Option 1 : FormSpree (Gratuit)

1. Créez un compte sur [FormSpree](https://formspree.io/)
2. Créez un nouveau formulaire
3. Dans `script.js` (ligne ~111), décommentez et modifiez :

```javascript
fetch('https://formspree.io/f/VOTRE_ID', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(formData)
})
.then(response => response.json())
.then(data => {
    showNotification('Merci pour votre message ! Nous vous répondrons très rapidement.', 'success');
    contactForm.reset();
})
.catch(error => {
    showNotification('Une erreur est survenue. Veuillez réessayer.', 'error');
});
```

### Option 2 : Netlify Forms

1. Ajoutez `netlify` à votre formulaire :
```html
<form class="contact-form" netlify>
```

2. Déployez sur Netlify - les formulaires seront automatiquement gérés

### Option 3 : Backend Personnalisé

Configurez votre propre API et modifiez l'URL dans `script.js` :
```javascript
fetch('/api/contact', { ... })
```

## 🎭 Changer les Typographies

### Police Actuelle

- **Titres** : Cormorant Garamond
- **Texte** : Montserrat

### Changer les Polices

1. Trouvez vos polices sur [Google Fonts](https://fonts.google.com/)
2. Remplacez la ligne 8 dans `index.html` :

```html
<link href="https://fonts.googleapis.com/css2?family=VotrePolice:wght@300;400;600&display=swap" rel="stylesheet">
```

3. Modifiez les variables dans `styles.css` :

```css
:root {
    --font-title: 'Votre Police Titre', serif;
    --font-body: 'Votre Police Texte', sans-serif;
}
```

## 🏷️ Personnaliser le Logo

### Option 1 : Logo Texte (Actuel)

Modifiez ligne 25 dans `index.html` :
```html
<div class="logo">Votre Nom</div>
```

### Option 2 : Logo Image

Remplacez par :
```html
<div class="logo">
    <img src="images/logo.png" alt="Sarah Glam Beauty" height="40">
</div>
```

Ajoutez dans `styles.css` :
```css
.logo img {
    height: 40px;
    width: auto;
}
```

## 📱 Ajouter un Numéro de Téléphone

### Dans le Footer

Ajoutez une nouvelle section dans le footer (ligne ~340) :

```html
<div class="footer-contact">
    <h4>Contact</h4>
    <p>📞 06 XX XX XX XX</p>
    <p>📧 contact@sarahglambeauty.fr</p>
    <p>📍 Adresse du salon</p>
</div>
```

Ajustez la grille dans `styles.css` :
```css
.footer-content {
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
```

## 🌐 SEO : Meta Tags

Personnalisez les meta tags dans `index.html` (lignes 5-7) :

```html
<meta name="description" content="Votre description personnalisée (150-160 caractères)">
<meta name="keywords" content="extensions cils, maquillage, beauté, votre ville">
<title>Votre Nom | Soins Beauté Premium</title>
```

Ajoutez des meta tags Open Graph :

```html
<!-- Open Graph / Facebook -->
<meta property="og:type" content="website">
<meta property="og:url" content="https://votre-site.fr/">
<meta property="og:title" content="Sarah Glam Beauty | Soins Beauté Premium">
<meta property="og:description" content="Extensions de cils, soins du regard et maquillage premium">
<meta property="og:image" content="https://votre-site.fr/images/og-image.jpg">

<!-- Twitter -->
<meta property="twitter:card" content="summary_large_image">
<meta property="twitter:url" content="https://votre-site.fr/">
<meta property="twitter:title" content="Sarah Glam Beauty | Soins Beauté Premium">
<meta property="twitter:description" content="Extensions de cils, soins du regard et maquillage premium">
<meta property="twitter:image" content="https://votre-site.fr/images/og-image.jpg">
```

## 🎬 Ajuster les Animations

### Désactiver les Animations

Si vous préférez un site sans animations, commentez dans `script.js` (lignes 61-75) :

```javascript
// Commentez tout le bloc Intersection Observer
/*
const observerOptions = { ... };
const observer = new IntersectionObserver(...);
fadeElements.forEach(element => {
    observer.observe(element);
});
*/
```

### Modifier la Vitesse

Dans `styles.css`, ajustez la variable de transition :
```css
:root {
    --transition-smooth: all 0.5s ease; /* Changez 0.3s en 0.5s pour plus lent */
}
```

## 🛠️ Outils Recommandés

### Compression d'Images
- [TinyPNG](https://tinypng.com/) - Compression PNG/JPG
- [Squoosh](https://squoosh.app/) - Conversion WebP

### Optimisation
- [Google PageSpeed Insights](https://pagespeed.web.dev/)
- [GTmetrix](https://gtmetrix.com/)

### Hébergement Gratuit
- [Netlify](https://www.netlify.com/) - Recommandé
- [Vercel](https://vercel.com/)
- [GitHub Pages](https://pages.github.com/)

## 📋 Checklist Avant Publication

- [ ] Toutes les photos sont optimisées (< 200KB chacune)
- [ ] Les textes sont personnalisés
- [ ] Le formulaire de contact fonctionne
- [ ] Les liens sociaux sont à jour
- [ ] Les meta tags SEO sont configurés
- [ ] Le site est testé sur mobile
- [ ] Le site est testé sur différents navigateurs
- [ ] Le favicon est ajouté
- [ ] Google Analytics est configuré (optionnel)

## 🎯 Aller Plus Loin

### Ajouter un Système de Réservation

Intégrez des outils comme :
- **Calendly** : Intégration simple
- **Acuity Scheduling** : Plus de fonctionnalités
- **SimplyBook.me** : Solution complète

Exemple d'intégration Calendly :
```html
<div class="calendly-inline-widget" 
     data-url="https://calendly.com/votre-nom" 
     style="min-width:320px;height:630px;">
</div>
<script src="https://assets.calendly.com/assets/external/widget.js"></script>
```

### Ajouter un Chat en Direct

- **Tawk.to** (Gratuit)
- **Crisp** (Gratuit jusqu'à 2 agents)
- **Messenger de Facebook**

---

**Besoin d'aide ?** N'hésitez pas à consulter la documentation officielle :
- [MDN Web Docs](https://developer.mozilla.org/)
- [CSS-Tricks](https://css-tricks.com/)
- [W3Schools](https://www.w3schools.com/)
