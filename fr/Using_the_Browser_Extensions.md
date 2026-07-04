<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Marked inclut des extensions de navigateur qui vous permettent d'envoyer des URL de pages ou du contenu sélectionné directement dans Marked 3.

## Installer

Téléchargez et installez à partir de [https://markedapp.com/extensions](https://markedapp.com/extensions) :

- Firefox/Zen
- Chrome / Courageux / Bord
- Safari (fourni)

## Comment fonctionne l'extension

Lorsque vous cliquez sur un bouton d'extension, une URL personnalisée gérée par Marked 3 s'ouvre à l'aide du schéma `x-marked-3://markdownify`.

### `Markdownify URL`

Dans la fenêtre contextuelle de l'extension, cliquez sur **`Markdownify URL`** pour envoyer l'URL de la page actuelle à Marqué.

### `Markdownify Selection`

Dans la fenêtre contextuelle de l'extension, cliquez sur **`Markdownify Selection`** lorsque vous avez une sélection dans la page.

Marked reçoit le code HTML de la sélection actuelle et le convertit en Markdown.

### Sélectionner la section (mode de sélection de bloc)

![][1]

[1]: images/marked-3-chrome-1.jpg width=1280px height=800px class=center

Cliquez sur **Sélectionner une section** pour accéder au « mode de sélection de section » :

- Passez la souris sur la page pour mettre en surbrillance les éléments de bloc que vous pouvez sélectionner.
- Cliquez sur un bloc pour l'envoyer immédiatement à Marked (envoi unique).
- Cmd-cliquez sur les blocs pour sélectionner plusieurs blocs (Cmd-cliquez à nouveau pour supprimer un bloc).
- Appuyez sur Retour pour envoyer les blocs actuellement sélectionnés.
- Appuyez sur Echap pour annuler le mode de sélection de section.

Lors de la sélection, la fenêtre contextuelle fournit également des commandes de zoom pour vous aider à cliquer sur des sections petites ou denses :

![][2]

[2]: images/marked-3-chrome-2.jpg width=1280px height=800px class=center

- `-` effectue un zoom arrière
- **Ajuster la hauteur** effectue un zoom pour que la page s'adapte à la hauteur de la fenêtre d'affichage
- `+` zoome