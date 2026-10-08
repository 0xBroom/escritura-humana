---
name: escritura-humana
description: |
  Remove signs of AI-generated writing from Spanish text so it reads as written by a native speaker.
  Use whenever writing, editing, reviewing or rewriting anything in Spanish: emails, posts, docs,
  READMEs, proposals, articles, LinkedIn posts, CVs, cover letters, Wikipedia content. Also use when
  the user asks to "humanizar", "que no suene a IA", "que suene natural", "quitar el tono de ChatGPT",
  "revisar el estilo" or similar, even if they don't name this skill. Covers Spanish-specific tells
  that English guides miss: English calques, gerundio de posterioridad, Title Case headings,
  unclosed rayas, English number and quote formats, plus the classic patterns (inflated significance,
  promotional tone, vague attributions, rule of three, negative parallelisms, AI vocabulary).
---

# Escritura humana en español

Find and remove the patterns that make Spanish text sound machine-generated, then rewrite so it reads like a native speaker wrote it. Based on Wikipedia's "Signs of AI writing" (WikiProject AI Cleanup), adapted to Spanish. Many English tells don't transfer literally, and Spanish has tells of its own, mostly calques from English and typography that follows English rules.

All explanations here are in English to save tokens. All patterns, word lists and examples are in Spanish on purpose: they are the literal strings to detect. Never translate them when scanning, and always write the output in Spanish.

## Workflow

1. Identify register and variety. A Wikipedia article, a tech README, a LinkedIn post and a WhatsApp message need different fixes. Detect whether the text is peninsular or Latin American Spanish and keep it consistent (vosotros vs ustedes, ordenador vs computadora, coger, vale, etc.). Default to peninsular Spanish if there's no signal.
2. Scan for the patterns below. One isolated hit means little; clusters matter.
3. Rewrite the flagged parts. Keep every fact and the original meaning. Never invent data to replace vague phrasing: if the source has no concrete detail, cut the empty phrase rather than fabricate one, or flag it to the user with `[dato concreto aquí]`.
4. Add voice where the register allows it (see "Voice"). Skip this for neutral registers.
5. When reviewing rather than rewriting, list the patterns found with the quoted fragment and a proposed fix. Keep the list short and ordered by impact.

## Voice

Removing patterns is half the job. Clean but flat text is also obvious: same sentence length everywhere, no stance, no concrete detail, reads like a press release.

For personal or opinion registers (posts, emails, blogs, talks):
- Take a position. React to facts instead of listing pros and cons evenly.
- Vary rhythm. Una frase corta. Luego otra más larga que se toma su tiempo para llegar adonde va.
- Use first person when it fits.
- Prefer concrete detail over abstraction: a number, a name, a date, a place.
- Allow some looseness: common idioms, contractions of tone, a tangent.

For neutral registers (Wikipedia, technical docs, legal, academic): do not add opinions or first person. Voice there means precision, concrete facts and natural syntax, not personality.

Antes (limpio pero sin pulso):
> El evento tuvo una gran acogida. Asistieron numerosas personas. Las charlas fueron interesantes. Los organizadores se mostraron satisfechos.

Después:
> Esperábamos 200 personas y vinieron casi 400. Tuvimos que abrir una segunda sala a media mañana y aun así hubo gente viendo la charla de pie en el pasillo.

---

## Content patterns

**Inflated significance and legacy.** Generic claims that something is important or historic, with no data behind them.
Watch for: desempeña un papel fundamental, marcó un antes y un después, dejó una huella imborrable, un hito en, un testimonio de, legado duradero, impacto perdurable, sentó las bases, en el marco de un movimiento más amplio.

Antes: «La fundación del instituto en 1989 marcó un hito en la evolución de la estadística regional, enmarcándose en un movimiento más amplio de descentralización.»
Después: «El instituto se fundó en 1989 para publicar estadísticas regionales sin depender del INE.»

**Promotional tone.** Brochure or press-release language.
Watch for: impresionante, emblemático, vibrante, de renombre, incomparable, de primer nivel, enclave privilegiado, joya escondida, en el corazón de, una experiencia única, apuesta por, compromiso con.

Antes: «Situado en el corazón de la Vega Baja, el municipio es un enclave privilegiado que ofrece una experiencia única gracias a su vibrante oferta cultural.»
Después: «El municipio está en la Vega Baja, a 20 minutos de Alicante. En agosto celebra unas fiestas de moros y cristianos que atraen a gente de toda la comarca.»

**Notability padding.** Listing media mentions to make a subject look relevant.
Antes: «Ha sido entrevistado por diversos medios nacionales e internacionales y cuenta con una destacada presencia en redes sociales.»
Después: «En 2024 habló en El País sobre la regulación de la IA en el sector sanitario.»

**Superficial analysis via trailing clauses.** A sentence ends with a gerund or "lo que…" clause that interprets the fact with no source.
Watch for: …, lo que refleja; …, consolidando así; …, poniendo de manifiesto; …, lo cual subraya; …, evidenciando; …, contribuyendo a.

Antes: «El templo usa azul, verde y dorado, lo que refleja la profunda conexión de la comunidad con su entorno natural.»
Después: «El templo usa azul, verde y dorado. Según el arquitecto, los colores remiten al mar y a los campos de la zona.»

**Vague attributions.** Opinions attributed to nobody in particular.
Watch for: los expertos coinciden, según diversos estudios, muchos consideran, ha sido ampliamente reconocido, diversas fuentes señalan.
Fix: name the source, or drop the claim.

**Formulaic challenges and conclusions.** Closing sections like "Desafíos y perspectivas", "Retos actuales", "Conclusión", and the formula «A pesar de sus logros, X se enfrenta a diversos desafíos…» followed by generic problems. Also upbeat endings: «El futuro se presenta prometedor», «sin duda seguirá creciendo».
Fix: replace with specific facts, or cut.

**Didactic asides.** Signposting nobody needs.
Watch for: cabe destacar que, es importante señalar que, conviene tener en cuenta que, vale la pena mencionar que.
Fix: delete the lead-in and state the fact.

**Excessive hedging.** Stacked softeners to avoid committing.
Watch for: podría decirse que, en cierta medida, de alguna manera, tiende a, es posible que, en cierto modo, probablemente (used reflexively).
Antes: «Podría considerarse, en cierto modo, uno de los posibles precursores del género.»
Después: «Fue uno de los precursores del género, según Pérez (2019).» Or simply: «Es uno de los precursores del género.»

---

## Language patterns

**AI vocabulary.** Not wrong individually; suspicious in clusters.
- Verbos: profundizar, fomentar, potenciar, subrayar, resaltar, destacar, abordar, impulsar, desempeñar un papel, sentar las bases, poner de relieve, poner de manifiesto
- Sustantivos: panorama, ecosistema, tapiz, sinergia, crisol, hito, testimonio, enclave, legado, trayectoria, interacción, complejidad
- Adjetivos: crucial, fundamental, clave, vibrante, emblemático, integral, dinámico, innovador, enriquecedor, intrincado, valioso, duradero
- Locuciones: en el corazón de, en el ámbito de, en el panorama actual, un rico tapiz de, a lo largo de los años, en constante evolución, no es de extrañar que, en un mundo cada vez más
- Conectores: además, asimismo, por otro lado, en este sentido, en definitiva, en resumen, en conclusión

Fix: use the plain word, or cut. «Juega un papel crucial en» → «sirve para», «es lo que permite», or the concrete action.

**Odd uses of "ser".** In English the tell is avoiding the copula. In Spanish it goes two ways:
- Promotional text replaces "es" with se erige como, se posiciona como, constituye, representa, funciona como. Fix: use «es» / «tiene».
- Plain descriptive text repeats «X es…» in every sentence and never uses apposition or elision. Fix: merge and elide.

Antes: «La primera etapa es experimental. La segunda es más comercial. El tercer disco es el más conocido.»
Después: «Empezaron con discos experimentales, giraron hacia algo más comercial y con el tercero se dieron a conocer.»

**Negative parallelisms.** One of the strongest tells.
Watch for: no se trata solo de X, sino de Y; no es solo un X, es un Y; más que un X, es un Y; no solo… sino también (overused).
Antes: «No se trata únicamente de un festival de música, sino de un punto de encuentro entre culturas.»
Después: «El festival trae grupos de doce países y cada noche termina con una jam abierta.»

**Rule of three.** Triads everywhere: «innovador, inclusivo y sostenible», «pasión, compromiso y creatividad». One triad is fine. One per paragraph is a tell. Fix: keep the one or two items that carry meaning.

**Synonym cycling.** «La banda… el grupo… la formación… el conjunto… el cuarteto alicantino» in one paragraph. Fix: repeat the noun or use a pronoun. Spanish tolerates repetition better than school taught.

**False ranges.** «Desde la gastronomía hasta la arquitectura», «desde sus humildes inicios hasta su consagración». Fix: list what's actually covered, or cut.

**English calques.** The most Spanish-specific signal. Models often think in English and translate.
- Gerundio de posterioridad: «Fundó la empresa en 1998, convirtiéndose en líder del sector.» → «Fundó la empresa en 1998 y con los años se convirtió en líder del sector.»
- Overused periphrastic passive: «El proyecto fue desarrollado por el equipo» → «El equipo desarrolló el proyecto» or «Se desarrolló en…».
- Unneeded possessives: «levantó su mano» → «levantó la mano».
- Lexical calques: jugar un rol, aplicar a un puesto, en orden a, a nivel de (non-spatial), es por eso que, remarcable, evento (for acontecimiento), asumir (for suponer), eventualmente (for finalmente), soportar (for admitir/compatibilizar), honestamente as sentence opener.
- Excess explicit subject pronouns: «Ella fue a Madrid. Ella estudió allí.» → drop the pronoun.
- Adjective before noun by default (English order) where Spanish prefers it after.

**Filler.**
- «con el objetivo de lograr esto» → «para esto»
- «debido al hecho de que» → «porque»
- «en el momento actual» → «ahora»
- «tiene la capacidad de procesar» → «puede procesar»
- «es importante tener en cuenta que los datos muestran» → «los datos muestran»
- «llevar a cabo» → «hacer», «realizar» → the specific verb

---

## Style and typography

**Title Case headings.** «Historia Y Legado Cultural». In Spanish only the first word and proper nouns are capitalized (RAE). Very reliable tell, because native speakers rarely do this unprompted. Fix: «Historia y legado cultural».

**Bold overuse.** Concepts bolded throughout. Fix: remove; keep bold only where the format genuinely needs it.

**Inline-header lists.** Each item starts with a bold label and colon («**Innovación:** La empresa apuesta por…»). Fix: rewrite as prose when the content is narrative.

**Emojis** in headings or bullets of professional text. Remove.

**Rayas.** Models use the em dash English-style: one dash opening an aside that never closes, or glued to words. In Spanish the raya opens and closes («el autor —según sus biógrafos— nunca volvió») except at sentence end. Spaced hyphens ( - ) as dashes are also a tell. Fix: prefer commas, parentheses or a new sentence. If a raya stays, close it properly.

**Quotes.** Follow the document's convention. For formal or editorial Spanish prefer comillas angulares «», with “ ” for quotes inside quotes. For casual or web text straight quotes are fine. Curly English quotes as the only level in a formal Spanish text is a mild tell.

**Numbers and dates.** English formats leak in.
- Thousands with comma or decimals with period: «1,500 habitantes» → «1500 habitantes» (no separator up to four digits) or «15 000»; «3.5» → «3,5».
- Month-first or capitalized months: «octubre 8, 2026», «8 de Octubre» → «8 de octubre de 2026».
- Percent glued to number: «25%» → «25 %» (RAE recommends a space; match the document if it already uses no space consistently).
- 12-hour clock with am/pm in peninsular texts → 24-hour or «de la tarde».

**Colon overuse.** Spanish AI text overuses colons to introduce explanations («La clave es sencilla: …»). Fix: rewrite as a direct sentence.

---

## Chatbot residue

**Collaborative messages.** «¡Claro! Aquí tienes…», «Espero que te sea útil», «Si quieres, puedo ampliar…», «¿Te gustaría que…?». Delete.

**Knowledge-cutoff disclaimers.** «Según mi última actualización…», «No dispongo de información posterior a…», «Te recomiendo consultar fuentes actualizadas». Delete, and if the fact is uncertain, say so specifically or flag it.

**Sycophancy.** «¡Excelente pregunta!», «Tienes toda la razón», «Gracias por tu valiosa aportación», repeated apologies, agreeing with every side. Fix: address the point directly.

**Unfilled placeholders.** «[Nombre de la empresa]», «[insertar fecha]», «XX». Flag to the user; never invent the value.

**Tool artifacts.** Markdown in contexts that don't render it, `turn0search0`, `:contentReference[oaicite:0]`, `utm_source=chatgpt.com` in URLs. Remove.

---

## Full example

Antes:
> La nueva actualización del software se erige como un testimonio del firme compromiso de la empresa con la innovación. Además, ofrece una experiencia fluida, intuitiva y potente —garantizando que los usuarios alcancen sus objetivos de manera eficiente. No se trata solo de una actualización, sino de una auténtica revolución en la productividad. Los expertos del sector coinciden en que tendrá un impacto duradero, consolidando el papel crucial de la compañía en el panorama tecnológico actual.

Después:
> La actualización añade procesamiento por lotes, atajos de teclado y modo sin conexión. En la beta, la mayoría de los usuarios tardó menos en completar las tareas habituales.

Changes: removed «se erige como un testimonio» (copula substitution, inflated significance), «Además» (AI connector), «fluida, intuitiva y potente» (rule of three, promotional), the unclosed raya and the trailing gerund «garantizando» (English punctuation, superficial analysis), «No se trata solo de… sino de…» (negative parallelism), «Los expertos del sector coinciden» (vague attribution), «impacto duradero», «papel crucial», «panorama» (AI vocabulary), «consolidando» (trailing gerund). Added concrete features and the beta result.

---

## What not to treat as a tell

- Perfect spelling and grammar. Many people write well.
- A formal or plain register when the context calls for it.
- A single «además», a single raya or a single triad.
- Non-native Spanish. Learner errors and translation habits are not AI signs.
- AI-detector scores. They are unreliable, worse in Spanish than in English.

## Reference

Adapted from Wikipedia's "Signs of AI writing" (https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), its Portuguese and French versions, and factory-ai/factory-plugins `human-writing`. Spanish-specific patterns (calques, typography, copula behavior) added for this version.
