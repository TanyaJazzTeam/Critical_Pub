# 1111

# 222

# TensorFlow documentation style guide

## Empfohlene Vorgehensweise

- Konzentrieren Sie sich auf die Benutzerabsicht und das Publikum.
- Verwenden Sie alltägliche Wörter und halten Sie die Sätze kurz.
- Verwenden Sie konsistente Satzkonstruktionen, Formulierungen und Großschreibung.
- Verwenden Sie Überschriften und Listen, um das Scannen Ihrer Dokumente zu erleichtern.
- Der [Styleguide für Google Developer Docs](https://developers.google.com/style/highlights) ist hilfreich.

## Abschlag

Mit wenigen Ausnahmen verwendet TensorFlow eine Markdown-Syntax ähnlich der von [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/) (GFM). In diesem Abschnitt werden die Unterschiede zwischen der GFM-Markdown-Syntax und dem für die TensorFlow-Dokumentation verwendeten Markdown erläutert.

### Über Code schreiben

#### Inline-Erwähnungen von Code

Setzen Sie <code>`backticks`</code> um die folgenden Symbole, wenn Sie sie im Text verwenden:

- Argumentnamen: <code>`input`</code> , <code>`x`</code> , <code>`tensor`</code>
- Zurückgegebene <code>`output`</code> , <code>`idx`</code> , <code>`out`</code>
- Datentypen: <code>`int32`</code> , <code>`float`</code> , <code>`uint8`</code>
- Andere Verweise auf <code>`list_diff()`</code> , <code>`shuffle()`</code>
- Klassennamen: <code>`tf.Tensor`</code> , <code>`Strategy`</code>
- Dateiname: <code>`image_ops.py`</code> , <code>`/path_to_dir/file_name`</code>
- Mathematische Ausdrücke oder Bedingungen: <code>`-1-input.dims() &lt;= dim &lt;= input.dims()`</code>

#### Code blocks

Verwenden Sie drei Backticks, um einen Codeblock zu öffnen und zu schließen. Geben Sie optional die Programmiersprache nach der ersten Backtick-Gruppe an, zum Beispiel:

<pre><code>
```python
# some python code here
```
</code></pre>

### Links in Markdown

#### Links zwischen Dateien in diesem Repository

Verwenden Sie relative Links zwischen Dateien in einem Repository. Dies funktioniert auf [tensorflow.org](https://www.tensorflow.org) und [GitHub](https://github.com/tensorflow/docs/tree/master/site/en) :<br> <code>\[Custom layers\]\(../tutorials/eager/custom_layers.ipynb\)</code> erstellt [benutzerdefinierte Ebenen](https://www.tensorflow.org/tutorials/eager/custom_layers) auf der Site.

#### Links zur API-Dokumentation

API-Links werden konvertiert, wenn die Site veröffentlicht wird. Um auf die API-Referenzseite eines Symbols zu verlinken, schließen Sie den vollständigen Symbolpfad in Backticks ein:

- <code>`tf.data.Dataset`</code> erzeugt [`tf.data.Dataset`](https://www.tensorflow.org/api_docs/python/tf/data/Dataset)

Verwenden Sie für die C++-API den Namespace-Pfad:

- `tensorflow::Tensor` erzeugt [tensorflow::Tensor](https://www.tensorflow.org/api_docs/cc/class/tensorflow/tensor)

#### Externe Links

Verwenden Sie für externe Links, einschließlich Dateien auf <var>https://www.tensorflow.org</var> , die sich nicht im `tensorflow/docs` , Standard-Markdown-Links mit dem vollständigen URI.

Um zum Quellcode zu verlinken, verwenden Sie einen Link, der mit <var>https://www.github.com/tensorflow/tensorflow/blob/master/</var> beginnt, gefolgt vom Dateinamen, der beim GitHub-Stammverzeichnis beginnt.

Dieses URI-Benennungsschema stellt sicher, dass <var>https://www.tensorflow.org</var> den Link an den Zweig des Codes weiterleiten kann, der der Version der angezeigten Dokumentation entspricht.

Schließen Sie keine URI-Abfrageparameter in den Link ein.

`custom_layers.ipynb` verwenden Unterstriche für Leerzeichen, beispielsweise custom_layers.ipynb .

Fügen Sie die Dateierweiterung in Links ein, die auf der Website *und auf* GitHub verwendet werden sollen, zum Beispiel:<br> <code>\[Custom layers\]\(../tutorials/eager/custom_layers.ipynb\)</code> .

### Mathe im Markdown

Sie können MathJax innerhalb von TensorFlow verwenden, wenn Sie Markdown-Dateien bearbeiten, beachten Sie jedoch Folgendes:

- MathJax rendert ordnungsgemäß auf [tensorflow.org](https://www.tensorflow.org) .
- MathJax rendert auf GitHub nicht richtig.
- Diese Notation kann für unbekannte Entwickler abschreckend sein.
- Aus Konsistenzgründen [folgt tensorflow.org](https://www.tensorflow.org) denselben Regeln wie Jupyter/Colab.

Verwenden Sie <code>$$</code> um einen Block von MathJax:

<pre><code>$$
E=\frac{1}{2n}\sum_x\lVert (y(x)-y'(x)) \rVert^2
$$</code></pre>

$$ E=\frac{1}{2n}\sum_x\lVert (y(x)-y'(x)) \rVert^2 $$

Wrap Inline MathJax-Ausdrücke mit <code>$ ... $</code> :

<pre><code>
This is an example of an inline MathJax expression: $ 2 \times 2 = 4 $
</code></pre>

Dies ist ein Beispiel für einen Inline-MathJax-Ausdruck: $ 2 \times 2 = 4 $

<code>\( ... \)</code> Trennzeichen funktionieren auch für Inline-Mathematik, aber das $-Formular ist manchmal besser lesbar.

Hinweis: Wenn Sie ein Dollarzeichen in Text oder MathJax-Ausdrücken verwenden müssen, maskieren Sie es mit einem führenden Schrägstrich: `\$` . Dollarzeichen innerhalb von Codeblöcken (wie Bash-Variablennamen) müssen nicht mit Escapezeichen versehen werden.

## Prosa-Stil

Wenn Sie wesentliche Teile der narrativen Dokumentation schreiben oder bearbeiten möchten, lesen Sie bitte den Styleguide für die [Google-Entwicklerdokumentation](https://developers.google.com/style/highlights) .

### Prinzipien des guten Stils

- *Überprüfen Sie die Rechtschreibung und Grammatik in Ihren Beiträgen.* Die meisten Editoren enthalten eine Rechtschreibprüfung oder ein verfügbares Rechtschreibprüfungs-Plugin. Sie können Ihren Text auch in ein Google-Dokument oder eine andere Dokumentsoftware einfügen, um eine zuverlässigere Rechtschreib- und Grammatikprüfung zu erhalten.
- *Verwenden Sie eine lockere und freundliche Stimme.* Schreiben Sie die TensorFlow-Dokumentation wie ein Gespräch – als würden Sie mit einer anderen Person eins zu eins sprechen. Verwenden Sie im Artikel einen unterstützenden Ton.

Hinweis: Weniger formell zu sein bedeutet nicht, weniger technisch zu sein. Vereinfachen Sie Ihre Prosa, nicht den technischen Inhalt.

- *Vermeiden Sie Haftungsausschlüsse, Meinungen und Werturteile.* Wörter wie „einfach“, „nur“ und „einfach“ sind voller Annahmen. Etwas mag Ihnen leicht erscheinen, aber für eine andere Person schwierig sein. Versuchen Sie diese nach Möglichkeit zu vermeiden.
- *Verwenden Sie einfache, prägnante Sätze ohne komplizierten Jargon.* Zusammengesetzte Sätze, Satzketten und ortsspezifische Redewendungen können dazu führen, dass Texte schwer zu verstehen und zu übersetzen sind. Wenn ein Satz in zwei Teile geteilt werden kann, sollte er es wahrscheinlich tun. Vermeiden Sie Semikolons. Verwenden Sie gegebenenfalls Aufzählungslisten.
- *Kontext bereitstellen.* Verwenden Sie keine Abkürzungen, ohne sie zu erklären. Erwähnen Sie keine Nicht-TensorFlow-Projekte, ohne sie zu verlinken. Erklären Sie, warum der Code so geschrieben ist, wie er ist.

## Gebrauchsanweisung

### Ops

Verwenden Sie `# ⇒` anstelle eines einzelnen Gleichheitszeichens, wenn Sie anzeigen möchten, was eine Operation zurückgibt.

```python
# 'input' is a tensor of shape [2, 3, 5]
(tf.expand_dims(input, 0))  # ⇒ [1, 2, 3, 5]
```

### Tensoren

Wenn Sie im Allgemeinen von einem Tensor sprechen, schreiben Sie das Wort *tensor* nicht groß. Wenn Sie über das spezifische Objekt sprechen, das einer *Operation bereitgestellt oder von einer Operation zurückgegeben wird, sollten Sie das Wort Tensor* groß schreiben und Backticks hinzufügen, da Sie von einem `Tensor` Objekt sprechen.

Sie nicht das Wort *Tensoren* (Plural) verwenden , um zu beschreiben mehrere `Tensor` - Objekte , wenn Sie wirklich sprechen von einem `Tensors` - Objekt. Sagen Sie stattdessen "eine Liste (oder Sammlung) von `Tensor` Objekten".

Verwenden Sie das Wort *Form,* um die Abmessungen eines Tensors anzugeben, und zeigen Sie die Form in eckigen Klammern mit Backticks an. Zum Beispiel:

<pre><code>
If `input` is a three-dimensional tensor with shape `[3, 4, 3]`, this operation
returns a three-dimensional tensor with shape `[6, 8, 6]`.
</code></pre>
