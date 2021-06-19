# Click to Tweet for Ghost (ver. 0.1 2021-06-19)

### Code iniection
Aggiungere in **Code iniection/Site Header**
~~~
div.notice-tweet {
	background-color:#f8f8f8;
	border: 1px solid #1da1f2;
	border-radius: 10px;
}
~~~

Aggiungere in **Code iniection/Site Footer**
~~~
<!-- Font Awesome -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
~~~

### Card HTML
Aggiungere al post, oppure alla pagina, una card HTML tramite il pulsante <code>+</code> e inserire il seguente codice:
~~~
<div class="notice-tweet" style="margin:50px 25px 50px 25px; padding:15px 10px 15px 10px; text-align:center;">
  <i class="fa fa-twitter-square fa-2x" style="color:#1DA1F2;"> </i>
    <div class="block-group__inner-container" style="margin:0px; padding:5px 10px 0px 5px; text-align:center;">
      <h10 style="color:#444; font-size:24px; font-weight:400;">Inserisci il testo che preferisci...</h10>
    </div>
</div>
<script>
const quotes = [...document.querySelectorAll('h10')];
if (quotes.length) {
	quotes.map(quote => {
		const content = quote.innerHTML;
		quote.innerHTML = content + ` <br><br><a href="https://twitter.com/intent/tweet/?url=${window.location.href}&text=${encodeURI(content)}" target="_blank">Condividi su Twitter</a>`;
	});
}
</script>
~~~

**NB: Ricordati di sostituire il testo "Inserisci il testo che preferisci..." con quello che preferisci.

### Esempio di utilizzo
Vedi [questo post](https://www.bertagna.it/creare-portfolio-fotografico/) che ho scritto sul mio Blog
