## Знакомство с кухней тестировщиков

#### или интересное путешествие в пучину хаоса

---
### Основные тезисы
- Зачем нужны логи тестирования |
- Цели и средсва |
- Понимание проведения автотестирования "на кошках" |
- Попытка "увидеть" сделанное |
- "Готовим" логи правильно или "Почему ReportPortal" |
- Камушки |

---
## Зачем нужны логи тестирования
- Помощь в оценке качества продукта |
- Помощь в оценке рисков |

Note:

Качество - хитрое понятие которое не просто замерять. Одной из характеристик качества является зрелость - отсуствие багов в устоявшейся части кода. Это и есть одна из причин тестирования API - этот код должен быть стабилен. И при первом появлении дистабилизируещего кода - сразу увидим результат.

Помогаем владельцам продукта, руководству проекта получить оценку рисков того, что ПО поведёт себя не так, как ожидается. Мы оцениваем, насколько компании и пользователям будет хуже, если мы выпустим продукт определённой баговости.
---
## Цели и средсва
- Начать составлять историю багов как часть видения прогресса продукта |
- Найти и понять, какие из средст самые популярные, модные, эфективные |

Note:

Сейчас у нас нет истории успешности или неуспешности завершения задачи/спринта и т.п. И общая цель будет в том, что мы сможем проанализировать не только запомнив, в голове, как и когда какой спринт был завершён, но и увидев быстро и наглядно, что когда задачи напирмер касаются тарифов и делаются быстро и/или оторвано от смежных, то баги и исправления как из рога изобилия.

Это было сделано раньше, чем полное понимание пункта выше, и наверное и явилось причиной "прогулкой в пучину" Была начата попытка понять, в какую сторону вообще смотреть, какие сайты открытвать, чтобы понять где найти то, не знаю что. Потому что понимания что именно нужно не было совсем, как что и куда должно идти, лететь и вообще вот это вот всё. Собственно это и было знакомство со средсвами автоматизированного тестирования, точнее со средствами уже более мнее познакомился, а теперь знакомился уже с тем, ради чего их используют - результаты. Благодоря хорошим людям (Санжар) была осознанна важнейшая ошибка - то что мы запускаем в интельке и видим там - совершенно не помогает и почти бесполезно. Оказалось что надо собирать проект, результатом которого был "сайт с результатами". 
---
## Понимание проведения автотестирования "на кошках"

Note:

Пришло понимание что надо запускать их как то скопом, и по определённому сценарию или типа того, это пока было не понятно.
Все эти дальнейшие результаты делались с большой помощью Руслана, Магжана (ненастоящий), Санжара, и тесты там ещё очень сильно не работали по внутренним причинам (у тестировщиков лапки).
+++
<!-- .slide: data-transition="none" -->
![1](assets/image/1.jpg)

Note:

Вот это вот то, что мне сразу не понравилось - sufefire - выглядит совсем не очень, и каждый раз надо куда-то это пересохранять накаплаивающиеся результаты. Сразу думал как Иван будет писать скрипт чтобы они куда-то складывались, датировались... Гемор тот ещё.
+++
<!-- .slide: data-transition="none" -->
![2](assets/image/2.jpg)

Note:

А вот это выглядело интересно - allure - графики по моему всегда более наглядны чем сухие цыферки. Хоть настоящих логов вы и не писали, но уже какое-то приятное ощущение было. Хотя с историей отчётов - та же беда.
+++
<!-- .slide: data-transition="none" -->
![3](assets/image/3.jpg)

Note:

Вот что-то такое, для меня ещё совсем не понятное также было найдено гуглом, но что, я ещё не знал что это и как. (ReportPortal)
---?code=sample/go/server.go&lang=golang&title=Golang File

@[1,3-6](Present code found within any repo source file.)
@[8-18](Without ever leaving your slideshow.)
@[19-28](Using GitPitch code-presenting with (optional) annotations.)

---

@title[JavaScript Block]

<p><span class="slide-title">JavaScript Block</span></p>

```javascript
// Include http module.
var http = require("http");

// Create the server. Function passed as parameter
// is called on every request made.
http.createServer(function (request, response) {
  // Attach listener on end event.  This event is
  // called when client sent, awaiting response.
  request.on("end", function () {
    // Write headers to the response.
    // HTTP 200 status, Content-Type text/plain.
    response.writeHead(200, {
      'Content-Type': 'text/plain'
    });
    // Send data and end response.
    response.end('Hello HTTP!');
  });

// Listen on the 8080 port.
}).listen(8080);
```

@[1,2](You can present code inlined within your slide markdown too.)
@[9-17](Displayed using code-syntax highlighting just like your IDE.)
@[19-20](Again, all of this without ever leaving your slideshow.)

---?gist=onetapbeyond/494e0fecaf0d6a2aa2acadfb8eb9d6e8&lang=scala&title=Scala GIST

@[23](You can even present code found within any GitHub GIST.)
@[41-53](GIST source code is beautifully rendered on any slide.)
@[57-62](And code-presenting works seamlessly for GIST too, both online and offline.)

---

## Template Help

- [Code Presenting](https://github.com/gitpitch/gitpitch/wiki/Code-Presenting)
  + [Repo Source](https://github.com/gitpitch/gitpitch/wiki/Code-Delimiter-Slides), [Static Blocks](https://github.com/gitpitch/gitpitch/wiki/Code-Slides), [GIST](https://github.com/gitpitch/gitpitch/wiki/GIST-Slides) 
- [Custom CSS Styling](https://github.com/gitpitch/gitpitch/wiki/Slideshow-Custom-CSS)
- [Slideshow Background Image](https://github.com/gitpitch/gitpitch/wiki/Background-Setting)
- [Slide-specific Background Images](https://github.com/gitpitch/gitpitch/wiki/Image-Slides#background)
- [Custom Logo](https://github.com/gitpitch/gitpitch/wiki/Logo-Setting), [TOC](https://github.com/gitpitch/gitpitch/wiki/Table-of-Contents), and [Footnotes](https://github.com/gitpitch/gitpitch/wiki/Footnote-Setting)

---

## Go GitPitch Pro!

<br>
<div class="left">
    <i class="fa fa-user-secret fa-5x" aria-hidden="true"> </i><br>
    <a href="https://gitpitch.com/pro-features" class="pro-link">
    More details here.</a>
</div>
<div class="right">
    <ul>
        <li>Private Repos</li>
        <li>Private URLs</li>
        <li>Password-Protection</li>
        <li>Image Opacity</li>
        <li>SVG Image Support</li>
    </ul>
</div>

---

### Вопросы?

<br>

@fa[twitter gp-contact](@gitpitch)

@fa[github gp-contact](gitpitch)

@fa[medium gp-contact](@gitpitch)

---?image=assets/image/gitpitch-audience.jpg

@title[Download this Template!]

### <span class="white">Get your presentation started!</span>
### [Download this template @fa[external-link gp-download]](https://gitpitch.com/template/download/aqua)
