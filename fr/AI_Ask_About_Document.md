<!-- MT-DRAFT: machine translation; human review required -->

# <%= @title %>

Ask About Document utilise **Apple Intelligence** et le modèle linguistique intégré aux versions récentes de macOS pour résumer votre aperçu Markdown et répondre aux questions sur son contenu. All processing happens on your Mac; le texte du document n'est pas envoyé aux serveurs de Marked ou aux services d'IA tiers pour cette fonctionnalité.

## What Apple Intelligence provides

Apple Intelligence est le système d'Apple pour les fonctionnalités génératives sur l'appareil. Marked utilise le framework **Foundation Models** d'Apple pour accéder au même modèle sur l'appareil qui alimente les outils d'écriture système, exposé directement dans Marked pour les tâches axées sur les documents.

Marked sends your document's plain text (Markdown syntax stripped for clarity) to this local model. The model generates summaries, outlines, and answers in a floating panel beside your preview window. Étant donné que le modèle s’exécute localement, il fonctionne hors ligne une fois qu’Apple Intelligence est configuré et que le téléchargement du modèle système est terminé.

Apple Intelligence is best at language tasks such as summarization, outlining, extracting key points, and answering questions about provided text. It is not a general coding assistant or calculator, and very long documents are handled in sections so results stay within the model's context limits.

## System compatibility

Demander à propos du document apparaît uniquement lorsque votre Mac peut exécuter la fonctionnalité.

**Required:**

- **macOS 26 (Tahoe)** or later
- Un **Mac avec prise en charge Apple Intelligence** (Mac Apple Silicon qui répondent aux exigences des appareils Apple)
- **Apple Intelligence activée** dans les paramètres système

**Not supported:**

- Intel Macs and other Macs marked as ineligible for Apple Intelligence
- macOS versions earlier than Tahoe 26
- Raw **HTML previews** (the feature is for Markdown and text-based document workflows)

If your Mac qualifies but the menu item is missing, confirm that Apple Intelligence is enabled and that you are running a current build of Marked that includes this feature. Le menu est entièrement masqué sur les systèmes non pris en charge plutôt que affiché dans un état désactivé.

## Enabling Apple Intelligence

1. Open **System Settings**.
2. Accédez à **Apple Intelligence & Siri** (ou **Apple Intelligence**, selon votre version de macOS).
3. Activez **Apple Intelligence** et effectuez toutes les étapes de configuration demandées par Apple.
4. Attendez que le modèle sur l'appareil termine le téléchargement si vous y êtes invité. Jusqu'à ce que le modèle soit prêt, Marked peut afficher l'élément de menu mais afficher un message indiquant qu'Apple Intelligence est toujours en train de préparer.

Marked does not include a separate preference for this feature. Availability follows the system model status reported by macOS.

## Opening Ask About Document

Open the panel using any of these methods:

- **Preview > Ask About Document…**
- Raccourci clavier {% kbd shift ctrl cmd I %} (tandis qu'un document d'aperçu Markdown est la fenêtre active)

The panel docks to the left side of the document window. You need an open document with readable text; un document vide ou un aperçu HTML uniquement ne proposera pas la commande.

## The Ask About Document panel

The panel is organized like a simple chat view:

- **Preset actions** at the top for common tasks
- Une **zone de réponse** au milieu où apparaissent les résumés et les réponses (en streaming au fur et à mesure de leur génération)
- Un **champ de question** en bas où vous saisissez des questions personnalisées, avec les boutons **Demander** et **Annuler**.

After a response completes, focus returns to the question field so you can ask a follow-up without clicking.

### Preset actions

| Action | What it does |
| :-- | :-- |
| **Summarize Document** | Produit un bref résumé cohérent du document complet. Long documents are summarized in sections and combined. |
| **Summarize Selection** | Summarizes only the text currently selected in the preview. Select text first; otherwise Marked prompts you to make a selection or use Summarize Document. |
| **Outline** | Builds a hierarchical outline of the document structure using headings and bullet points. |
| **Key Points** | Lists the most important points from the document as a bullet list. |

Preset actions do not require text in the question field. Click a button and wait for the response in the panel above.

### Poser vos propres questions

1. Type a question in the field at the bottom of the panel, for example "What problem does this document solve?" ou "Quel est le public visé ?"
2. Appuyez sur **Retour** ou cliquez sur **Demander**.
3. Read the answer as it streams into the response area.

Pour des questions sur un passage spécifique, **sélectionnez ce texte dans l'aperçu** avant de poser la question. Marked sends the selection as context instead of the whole document when a selection is active.

Cliquez sur **Annuler** pour arrêter une demande en cours.

## Examples

### Aperçu rapide d'un long article

Ouvrez un long article de blog ou un rapport dans Marqué, choisissez **Aperçu > Demander à propos du document…**, puis cliquez sur **Résumer le document**. Use the summary to decide whether to read the full piece or to refresh your memory after time away from the draft.

### Notes on a selected paragraph

Highlight a dense paragraph in the preview, open Ask About Document, and click **Summarize Selection**. Useful when you only need a shorter version of one section.

### Structural review

Click **Outline** on a draft with many headings to see whether the argument flows logically, or use **Key Points** before sending a document to someone else to check that the main ideas are clear.

### Targeted questions

With no selection active, type questions such as:

- "Quelles sont les trois principales recommandations ?"
- "Does this document mention licensing?"
- "List any dates or deadlines mentioned."

With a selection active, ask narrower questions such as "What does this paragraph assume about the reader?" or "Rewrite this idea in one sentence" (the model answers about the selection; it does not edit your source file).

## Tips and limitations

- **Privacy:** Processing uses Apple's on-device model. Marked still reads your document text locally to provide content to that model; traiter les matériaux sensibles en conséquence.
- **Accuracy:** Verify important facts against your source. AI summaries can omit details or misread ambiguous passages.
- **Length:** Extremely long documents are processed in chunks. Summaries and answers reflect the full text indirectly; for precision on one section, select that section first.
- **Language:** Results follow the language capabilities of the system Apple Intelligence model on your Mac.
- **Refusals:** The system may decline some requests based on Apple's safety policies.

Si Demander à propos du document n'est pas disponible, vérifiez l'état des paramètres système pour Apple Intelligence et assurez-vous de prévisualiser un document Markdown sur un Mac pris en charge exécutant macOS 26 ou version ultérieure.