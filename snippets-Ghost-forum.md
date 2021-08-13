# Raccolta di Snippets tratti dal [Forum di Ghost](https://forum.ghost.org/)

## INDICE
1. Nascondi il link a Ghost nel footer;

---

## Nascondi il link a Ghost nel footer
Codice da inserire in **Settings > Code injection** - [Post da cui è tratto](https://forum.ghost.org/t/code-injection-to-remove-ghost-link-from-caspar-footer-theme/16922/8)

~~~
<style>
/* Suppress the Ghost link in the footer. */
    .site-footer a[href="https://ghost.org/"] {
        display: none;
    }
</style>
~~~

## Nascondi il link a Ghost nel footer, CTA Membership e icone social in head
Codice da inserire in **Settings > Code injection** - [Post da cui è tratto](https://forum.ghost.org/t/ghost-4-0-really-terrible-for-personal-blog/20811/68)
~~~
<style type='text/css'>
    /* Hide the Membership aka Subscribe actions etc. */
    .footer-cta,
    .gh-head-actions,
    .site-footer a[href^="https://ghost.org"] { display: none; }
    .gh-head-inner { grid-template-columns: auto auto; }
    .gh-head-brand { max-width: 400px; }
    .gh-head-menu { justify-content: flex-end; }
</style>
~~~

## Tema Casper - Applica il tema scuro se impostato nel browser
Codice da inserire in **Settings > Code injection** - Tratto dal post: [Casper night mode not working](https://forum.ghost.org/t/casper-night-mode-not-working/24658/9)
~~~
<script>
const handleColorSchemePreferenceChange = event => {
    document.documentElement.classList.toggle('dark-mode', event.matches);
};

const systemThemeMatch = window.matchMedia('(prefers-color-scheme: dark)');
systemThemeMatch.addEventListener('change', handleColorSchemePreferenceChange);
// Set theme for first users. Since `systemThemeMatch` and `event` both have the matches property, we can reuse the preference change function
handleColorSchemePreferenceChange(systemThemeMatch);
</script>
~~~