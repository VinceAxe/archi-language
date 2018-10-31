# Translation

- based on [Archi : an Archimate tool](https://github.com/archimatetool/archi)
- based on [NLS Plugin](https://github.com/smeagol74/archi-nls)


##A way to translate efficiently

###Full initial cinematic

1. The master branch is still [Archi](https://github.com/archimatetool/archi)
2. From the master branch, the english language is run from the ant script provided by the [NLS Plugin](https://github.com/smeagol74/archi-nls)
3. a copy is done of the nls folder inside the "lang_en" branch
4. a new branch for the target language is added (for instance : "lang_fr")
5. The .en and nl/en folders have to be renamed in the target language
6. All *_en files have to be renamed in the target language (bash command :
'for i in $(find ./com.* -iname "*_en*"); do mv -v $i $(echo "$i" | sed -r 's|_en|_fr|g'); done'
)
7. Run the Ant script from the NLS plugin master branch, for the target language
8. Copy and replace all existing files in the target language branch

Objective : migrate from en properties and en file content to target properties but still english file contents
Thus the translation can be focused only on the content, and a rebase can be done only on the content part, with a real link from the english properties to the target properties.

9. This is the lg_fr_v0 tag

All french content are in the lang_fr branch

------
3. The translated branch has to be rebased
4. Treating all conflicts implies to update the translation


-------
More informations on the [official developper wiki](https://github.com/archimatetool/archi/wiki)
Even more on the [Archi Translating wiki](https://github.com/archimatetool/archi/wiki/Translating-Archi)
