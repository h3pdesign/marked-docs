# <%= @title %>

Si un fichier inclus via [la syntaxe d'inclusion de Marked ou la syntaxe de bloc iA Writer][include] a une extension CSV ou TSV, Marked tentera de l'analyser et de le convertir en table MultiMarkdown. Cela fonctionne avec la plupart des formats standards, y compris les formats séparés par des virgules et des tabulations, ainsi qu'avec des séparateurs supplémentaires et des formats de guillemets automatiquement détectés.

L'un des avantages de l'utilisation de fichiers CSV au lieu d'écrire des tableaux Markdown est que les sauts de ligne dans les cellules sont automatiquement convertis en balises `<br>`. Il faut faire cela manuellement pour inclure des sauts de ligne lors de la rédaction de tableaux MultiMarkdown, ce qui en fait un gain de temps supplémentaire.

En remarque, il existe une excellente application appelée [TableFlip][] qui facilite grandement l'édition des tableaux dans votre document. Cela vaut la peine de vérifier si vous travaillez fréquemment avec des données tabulaires.

Les fichiers CSV inclus seront surveillés pour détecter les modifications, afin que des modifications supplémentaires puissent être effectuées dans le fichier CSV d'origine et Marked mettra automatiquement à jour l'aperçu lors de l'enregistrement.

Les tableaux convertis seront inclus dans l'exportation Markdown, de sorte que Marked puisse être utilisé pour compiler des documents contenant des données structurées et exporter un seul fichier.

[include]: Multi-File_Documents.html
[TableFlip]: http://tableflipapp.com/
