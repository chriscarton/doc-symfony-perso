# PERSONNALISER LES PAGES D'ERREUR

Voir cette documentation :

https://symfony.com/doc/current/controller/error_pages.html

# Créer cette arborescence

    templates
        bundles
            TwigBundle
                Exceptions
                    error.404.html.twig
                    error.403.html.twig
                    error.html.twig

**error.html.twig** => toutes les autres erreurs.
