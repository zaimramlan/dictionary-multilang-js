# Description
A simple JS library to support multiple language (multi-lang) feature or translations on sites

# How it works
1. The `JSON` file will act as language packs that have different translations of the same text.
2. It loads up the language packs (that contains the text strings) from the supplied `JSON` file.
3. Initialise the elements with `data-dictionary` attribute with the text from the default language, set.
4. Change the `data-dictionary` elements, based on the selected language, by toggling the buttons

**Note:**  
The value for the `data-dictionary` attribute is the location of the text string inside the `JSON` file.  
Example:  

`lang.english.json`
```
{
	"body": {
		"some_heading" : "your header text",
		"some_other_heading": "anyone\'s header text"
	}
}
```

`lang.thai.json`
```
{
	"body": {
		"some_heading" : "ข้อความส่วนหัวของคุณ",
		"some_other_heading": "ข้อความส่วนหัวของทุกคน"
	}
}
```

`your_page.html`
```
<!-- The value within the <h1> tag will be 
'your header text' or 'ข้อความส่วนหัวของคุณ' -->
<h1 data-dictionary="body.some_heading"></h1>
```

# Dependencies
- jQuery

# Installation
Simply download the multi-lang package file `dictionary.js` into your website folder and you are ready to go!

# Usage
1) Import multi-lang-js package
```
<script src="path/to/dictionary.js"></script>
```

2) Initialise language packs
```
var dictionary = new Dictionary();
dictionary.init({
  en: 'path/to/lang.english.json',
  bm: 'path/to/lang.bahasa.json',
  th: 'path/to/lang.thai.json,
  default: 'en'
});
```

3) Initialise language toggle buttons
```
dictionary.initButtons({
  en: 'btn-en',
  bm: 'btn-bm',
  th: 'btn-th'  
});
```

4) Tag the elements that you want translated, with `data-dictionary="text.location.in.JSON.tree"`
```
<h1 data-dictionary="body.some_heading.text"></h1>
```

5) Add the language buttons
```
<a class="btn-en">EN</a> | <a class="btn-bm">BM</a> | <a class="btn-th">TH</a>
```

That's it! The rest will magically happen when you simply toggle the languages.
  
Have fun!

# Styling
The active language button will automatically have the class `active-dictionary`. So you can simply style the active language by using the CSS class selector `.active-dictionary`
```
a.active-dictionary {
  text-decoration: underline;
}
```

# Making Changes
1. Create your feature branch (`git checkout -b new-feature`)  
2. Commit your changes (`git commit -am 'Some cool reflection'`)  
3. Push to the branch (`git push origin new-feature`)  
4. Create new Pull Request

# License
MIT
