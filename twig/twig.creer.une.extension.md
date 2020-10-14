# Créer une extension Twig :

Dans la console

    php bin/console make:twig-extension

    > AppExtension

Le fichier se trouve ici : **src/Twig/AppExtension.php**

Dans **getFunctions()**

    return[
        new TwigFunction('pluralize, [$this,'doSomething']),
    ]

Changer **function_name** par... ce qu'on veut.

Remplacer **doSomething** (appel et méthode) par... ce qu'on veut.

    public function doSomething(int $count, string $singular, ?string $plural):string
    {
        //Si $plural existe, ce sera $plural
        //Sinon ce sera $singular avec un 's'
        $plural ??= $singular.'s';

        //Si count est à 1 on utilise le singulier, sinon le pluriel
        $str = $count === 1 ? $singular : $plural;

        //Interpolation avec les doubles quotes ""
        return "$count $str";
    }

# Argument optionnel

    function doSomething(int $count, string $singular, ?string $plural=null)

**?**string \$plural signifie que cet argument est optionnel.

La valeur par défaut est **null**

# Utilisation de cette extension

Dans la vue :

    <h1>{{ pluralize(pins|length,'Pin') }}</h1>
