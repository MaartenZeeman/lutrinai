
<template>
  <article class="chat-content">
    <section class="message">
        <h2 class="question">Wat eten otters?</h2>
        <div class="answer">Otters eten voornamelijk dierlijk voedsel, omdat ze carnivoren zijn. Hun dieet varieert
            afhankelijk van de soort en de omgeving, maar over het algemeen bestaat het uit:
            <ul>
                <li>Vis – Dit is de hoofdbestanddeel van het dieet van veel ottersoorten, zoals de Europese en
                    zeeotters.</li>
                <li>Schaaldieren – Kreeften, krabben en garnalen vormen een belangrijk deel van hun voedsel, vooral voor
                    zeeotters.</li>
                <li>Kikkers en amfibieën – In zoetwatergebieden eten otters ook graag kikkers, padden en salamanders.
                </li>
                <li>Vogels – Soms vangen ze watervogels of hun eieren.</li>
                <li>Kleine zoogdieren – Sommige otters eten kleine zoogdieren zoals ratten en muizen.</li>
                <li>Insecten – Jonge otters of kleinere soorten eten ook insecten, vooral als andere voedselbronnen
                    schaars zijn.</li>
            </ul>
            Zeeotters gebruiken vaak stenen als gereedschap om schaaldieren open te breken, een unieke eigenschap die
            hun slimheid en handigheid aantoont.
        </div>
    </section>

    <section class="message">
        <h2 class="question">Hoe ruiken otters?</h2>
        <p class="answer">Otters hebben een vrij sterke geur, die afhankelijk van de soort en de omstandigheden kan
            variëren. Over het algemeen wordt de geur van otters beschreven als muskusachtig. Dit komt door klieren bij
            hun staart, die een geur afscheiden waarmee ze hun territorium markeren en communiceren met andere otters.
            De geur kan variëren van scherp en intens tot subtieler, afhankelijk van de otter en de tijd van het jaar
            (bijvoorbeeld tijdens het paringsseizoen is de geur vaak sterker).

            Sommige mensen beschrijven de geur als onaangenaam, vooral wanneer otters hun geurklieren gebruiken om hun
            territorium af te bakenen. Maar de dieren zelf gebruiken het om hun omgeving beter te begrijpen en sociale
            signalen af te geven.
        </p>
    </section>
  </article>

  <div class="chat-input-container">
    <input type="text" placeholder="Type a message..." class="chat-input" />
    <button class="btn">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor">
            <path d="M3 21v-6l13-3-13-3v-6l21 9-21 9z" />
        </svg>
    </button>
  </div>
</template>


<style scoped lang="scss">
  section {
    margin-bottom: 30px;
  }

  .question {
    font-size: 1.2rem;
    margin-bottom: 3px;
    border-bottom: 2px solid #ddd;
    font-style: italic;
    font-weight: bold;
  }

  .answer {
    white-space: pre-line;
  }

  ul {
    padding-left: 1.5rem;
  }

  /* ChatGPT generated input field. Might be ranzig */
  .chat-input-container {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    align-items: center;
    padding: 15px 30px 15px 30px;
    background-color: #EED2CC;
    color: #555;
    margin: 0 auto;
  }

  .chat-input {
    flex: 1;
    padding: 10px 15px;
    border: none;
    border-radius: 4px;
    background-color: #fff;
    outline: none;
    box-shadow: inset 0 2px 4px rgba(0, 0, 0, 0.05);
  }

  .chat-input::placeholder {
    color: #777;
  }
</style>
