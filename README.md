# escritura-humana

Skill para agentes (Claude Code, Codex, Cursor y cualquiera compatible con el formato de skills) que detecta los patrones típicos del texto generado por IA en español y los reescribe para que suene a alguien que escribe en su idioma.

La hice porque las skills que había para esto estaban pensadas para el inglés. Traducidas al español se quedan cortas. Buscan «delve» y «tapestry» y no ven lo que de verdad delata a un modelo escribiendo en castellano, que casi siempre es un calco del inglés o una regla tipográfica que no es la nuestra.

## Qué revisa

Los patrones clásicos de la guía de Wikipedia, adaptados con ejemplos en español.

- Importancia inflada («marcó un antes y un después», «dejó una huella imborrable»)
- Tono de folleto («en el corazón de», «enclave privilegiado», «una experiencia única»)
- Coletillas que interpretan el dato sin fuente («…, lo que refleja su compromiso con»)
- Atribuciones vagas («los expertos coinciden en que»)
- Paralelismos del tipo «no se trata solo de X, sino de Y»
- Tríos de adjetivos en cada párrafo
- Matizaciones apiladas y tono adulador
- Restos de la conversación con el chatbot («¡Claro! Aquí tienes…», `utm_source=chatgpt.com`)

Y lo que es propio del español, que es donde está la diferencia con otras skills.

- Gerundio de posterioridad («fundó la empresa en 1998, convirtiéndose en líder del sector»)
- Calcos como «jugar un rol», «aplicar a un puesto», «a nivel de» o «eventualmente» en el sentido de «finalmente»
- Pasiva perifrástica donde iría la activa y posesivos que sobran («levantó su mano»)
- Mayúsculas en cada palabra de los títulos, que en español no se usan
- Rayas que se abren y nunca se cierran
- Formatos ingleses de números y fechas («1,500 habitantes», «octubre 8»)
- Abuso de los dos puntos para presentar explicaciones

Antes de tocar nada identifica el registro y la variedad del texto. No corrige igual un README que un post de LinkedIn, y respeta si escribes con vosotros o con ustedes. Si no hay pistas, tira a español de España.

## Un ejemplo

Entrada

> La nueva actualización del software se erige como un testimonio del firme compromiso de la empresa con la innovación. Además, ofrece una experiencia fluida, intuitiva y potente, garantizando que los usuarios alcancen sus objetivos de manera eficiente. No se trata solo de una actualización, sino de una auténtica revolución en la productividad.

Salida

> La actualización añade procesamiento por lotes, atajos de teclado y modo sin conexión. En la beta, la mayoría de los usuarios tardó menos en completar las tareas habituales.

Ojo con esto. La salida tiene datos que la entrada no tenía porque en el ejemplo los aporta quien escribe. La skill tiene prohibido inventárselos. Si el texto original no tiene el detalle concreto, borra la frase vacía o deja un `[dato concreto aquí]` para que lo rellenes tú.

## Instalación

Con el CLI de skills

```bash
npx skills add https://github.com/0xBroom/escritura-humana
```

A mano en Claude Code

```bash
git clone https://github.com/0xBroom/escritura-humana.git ~/.claude/skills/escritura-humana
```

En Claude.ai puedes subir el archivo `.skill` desde la sección de skills de los ajustes.

## Uso

Se activa sola cuando le pides al agente que escriba o revise algo en español, o cuando usas expresiones como «humaniza esto», «que no suene a IA» o «quítale el tono de ChatGPT». También puedes llamarla por su nombre.

```
/escritura-humana revisa este correo antes de enviarlo
```

Si le pides una revisión en vez de una reescritura, te devuelve una lista corta con el fragmento problemático, el patrón y una propuesta de cambio.

## Por qué las instrucciones están en inglés

El `SKILL.md` explica cada patrón en inglés porque el español gasta bastantes más tokens con el mismo contenido y los modelos siguen igual de bien las instrucciones en inglés. Los ejemplos, las listas de vocabulario y los antes y después están en español a propósito. Son las cadenas que el agente tiene que reconocer, y traducirlas al inglés le haría buscar el calco y no la expresión real. La salida siempre es en español.

## Lo que no hace

No sirve para engañar a detectores de IA y no está pensada para eso. Esos detectores fallan mucho, más todavía en español, y un texto vacío sigue siendo vacío aunque pase el filtro. Lo que intenta es que el texto diga algo concreto y que lo diga como lo diría una persona.

Tampoco trata como señal de IA escribir sin faltas, un registro formal cuando toca o los errores de alguien que escribe en español como segunda lengua.

## Origen

Se basa en la página [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) de la Wikipedia en inglés, mantenida por el WikiProject AI Cleanup, y en sus versiones en [portugués](https://pt.wikipedia.org/wiki/Wikip%C3%A9dia:Sinais_de_texto_gerado_por_intelig%C3%AAncia_artificial) y [francés](https://fr.wikipedia.org/wiki/Aide:Identifier_l%27usage_d%27une_IA_g%C3%A9n%C3%A9rative). La estructura toma como referencia la skill [human-writing](https://www.skills.sh/factory-ai/factory-plugins/human-writing) de Factory. Los patrones propios del español salen de una adaptación de esa guía al castellano que preparé en paralelo para proponerla en la Wikipedia en español.

## Contribuir

Lo que más ayuda son los falsos positivos. Si la skill marca como IA algo que escribiste tú, o cambia una expresión que en tu zona es lo normal, abre un issue con el texto y la variedad de español que usas. También se agradecen patrones nuevos, sobre todo calcos que no estén en la lista.

## Licencia

[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.es), la misma que el contenido de Wikipedia del que deriva. Puedes usarla, modificarla y redistribuirla citando la fuente y manteniendo la misma licencia.
