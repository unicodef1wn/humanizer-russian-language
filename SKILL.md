---
name: humanizer-ru
version: 1.0.0
description: Removes signs of AI generation from Russian-language blog content and social media posts (Telegram, vc.ru, Habr and similar) while keeping a lively, readable style. Universal and voice-neutral — works for long articles, short posts, notes, news breakdowns and opinion pieces. Must be used when the user says "перепиши более живо" (rewrite it more lively), "сделай менее ИИ-шно" (make it less AI-ish), "звучит как ChatGPT" (sounds like ChatGPT), "слишком сухо/шаблонно" (too dry / formulaic), "выглядит как LinkedIn-пост" (looks like a LinkedIn post), "очисти от воды" (cut the fluff). Also apply proactively after generating any Russian blog text, post or article longer than a paragraph, before handing the result to the user. Do not use for academic or legal texts — humanizer-ru-legal exists for those. Do not use for greentext, reply copy and other genres with their own conventions.
license: MIT
---

# Humanizer for Russian blog content

The task is to remove signs of AI generation from Russian blog text (Telegram, vc.ru, Habr, articles, long posts, notes) while keeping a lively, readable style. This is not a "casual" rewrite down to the level of private messages; the goal is text that a competent author with their own voice could have written.

All examples and marker lists below are in Russian on purpose — they are the actual patterns the skill looks for in Russian text.

## Scope

**Covers:**
- Long posts for Telegram channels (narrative format)
- Articles on vc.ru, Habr, Medium-like platforms
- Analytical breakdowns and reviews
- Personal opinion pieces and essays
- Tutorials and how-tos (the prose part, not the code)

**Does not cover** (different rules apply):
- Greentext posts
- Short reply copy (1–2 sentences)
- Video scripts (spoken rhythm is different)
- Academic texts, theses, legal opinions — use `humanizer-ru-legal` for those

---

## Basic process

1. Read the whole draft and catch the impression: where it sounds like a LinkedIn post, where like a ChatGPT essay
2. Go through the marker checklist (Sections A–C)
3. Rewrite the problem spots — don't swap individual words, restructure the phrases
4. Run the final audit (counters + structural checks)
5. Make sure you haven't overshot into the opposite extreme (Section E)

**Core principle:** rhythm, specificity and focus matter more than a replacement dictionary. You can remove every AI word and still leave the text dead if all sentences are the same length with no living connection between them.

---

## Section A. AI markers in blog content (critical)

The most frequent markers by which a reader spots ChatGPT in a post within five seconds.

### A1. Grandiose openers

The most recognizable AI marker in blogs. The text opens with a global statement instead of entering the topic.

**Markers:**
- "В сегодняшнем мире, где..."
- "В современную эпоху..."
- "В эпоху, когда технологии развиваются стремительными темпами..."
- "В условиях стремительно меняющегося..."
- "На фоне растущего интереса к..."
- "С развитием X / появлением Y..."
- "В последние годы наблюдается тенденция..."
- "Невозможно переоценить роль X в..."

**Fix:** delete entirely. Start with a concrete fact, observation or claim about the topic.

**Before:**
> В современную эпоху, когда искусственный интеллект развивается стремительными темпами, всё больше компаний задумываются о внедрении AI-агентов в свои бизнес-процессы.

**After:**
> AI-агентов сейчас внедряют все подряд. Большинство — впустую.

### A2. The LinkedIn formula "here are N things I learned"

AI loves structuring a post as a motivational list with promised value.

**Markers:**
- "Вот 5 вещей, которые я понял о X"
- "3 урока, которые научили меня Y"
- "Делюсь опытом / лайфхаками / инсайтами"
- "Сохраняйте, пригодится"
- "Спасибо, что дочитали"
- "Если было полезно — ставьте 🔥"
- "Дайте знать в комментариях"

**Fix:** drop the formula. If the post really has N points — state them without the "here are 5 things" wrapper. Closing calls to action only if they are organic, not a ritual.

### A3. Mentor tone

AI often writes from the position of a "life coach", even when discussing a technical detail.

**Markers:**
- "Важно понимать, что..."
- "Главное здесь — осознать, что..."
- "Запомните: ..."
- "Не забывайте, что..."
- "Помните: ..."
- "Усвойте одну простую мысль:"
- "Ключ к успеху в..."
- "Секрет в том, что..."

**Fix:** remove the mentor wrapper. If the thought is interesting, it works without "важно понимать". If it sounds banal without the wrapper — it was banal.

**Before:**
> Важно понимать, что AI-агенты — это не магия, а просто инструмент.

**After:**
> AI-агенты — не магия, а инструмент.

### A4. Pseudo-depth tropes

AI pretends to be breaking through to the essence.

**Markers:**
- "по сути"
- "в сущности"
- "на самом деле"
- "если разобраться"
- "при ближайшем рассмотрении"
- "по большому счёту"
- "по факту"
- "истина в том, что"

**Fix:** delete. If content remains after deletion — keep it. If not — rewrite the whole phrase.

### A5. Throat-clearing openers

AI almost never gets straight to the point.

**Markers:**
- "стоит отметить, что"
- "следует упомянуть"
- "необходимо подчеркнуть"
- "хочется отметить"
- "интересно отметить, что"
- "обращает на себя внимание"
- "заслуживает внимания тот факт"
- "не лишним будет сказать"

**Fix:** delete entirely, leave the bare thought.

### A6. Bureaucratic register in a blog context

Normal in a thesis, an instant AI marker in a blog.

- **"осуществляется"** / **"производится"** → a concrete verb
- **"является"** → "это" / a dash / rephrase
- **"данный"** meaning "this" → "этот" or delete
- **"в рамках"** → can be removed in 80% of cases
- **"в части касающейся"** → delete
- **"в целях"** → "чтобы"
- **"в случае если"** → "если"
- **"в условиях"** → delete or make specific
- **"механизм"** meaning "how it works" → a concrete verb
- **"функционирование"** → "работа"
- **"реализация"** → "применение", "выполнение" or a verb
- **"обеспечение"** as a noun → a verb
- **"требования, предъявляемые к"** → "требования к"
- **"осуществление деятельности по"** → delete entirely, keep the verb

### A7. Emotional inflation

AI inflates the importance and emotional charge of everything.

**Markers:**
- "это меняет всё"
- "революционный подход"
- "переворачивает индустрию"
- "не имеет аналогов"
- "впечатляющий результат"
- "поразительно"
- "уникальная возможность"
- "беспрецедентный"
- "невероятный"
- "потрясающий"
- "колоссальный"

**Fix:** replace with specifics or delete. If it really "changes everything" — explain exactly how, without the epithet.

**Before:**
> Это революционная технология, которая меняет всё.

**After:**
> Технология сокращает время разработки агента с двух недель до двух часов.

### A8. Paired constructions

AI adores pairing.

- "как..., так и..."
- "не только..., но и..."
- "с одной стороны..., с другой стороны..."
- "и теоретически, и практически"

**Fix:** split into two sentences or list with commas.

**Before:**
> AI-агенты полезны как для автоматизации рутины, так и для сложных задач.

**After:**
> AI-агенты полезны и для рутины, и для сложных задач.

or:

> AI-агенты автоматизируют рутину. С чем посложнее — тоже справляются, если правильно настроены.

### A9. Participial tails

The sentence ends with a long "-ая/-яя/-ущ/-ющ/-вши" clause that adds nothing.

**Markers:** "подчёркивая", "отражая", "способствуя", "обусловливая", "формируя", "создавая", "представляя", "являясь", "обеспечивая", "позволяя"

**Fix:** cut the tail; if needed, move its content into a separate sentence.

**Before:**
> Многие компании внедряют AI-агентов, стремясь автоматизировать рутинные задачи и сократить издержки.

**After:**
> Многие компании внедряют AI-агентов — хотят сократить рутину и издержки.

### A10. Bureaucratic bridges between paragraphs

AI links paragraphs with template bridges.

**Markers:** "между тем", "вместе с тем", "помимо этого", "наряду с этим", "в свою очередь", "в этой связи", "в этом контексте", "что касается", "переходя к"

**Fix:** remove or replace with a short "Но", "Однако", "Ещё", "Дальше", "А вот", "При этом".

### A11. Upbeat ending

The most recognizable AI marker in a blog — a motivational-speaker finale.

**Markers:**
- "открывает новые горизонты"
- "знаменует новый этап"
- "будущее уже здесь"
- "перспективы безграничны"
- "пришло время действовать"
- "одно можно сказать точно: ..."
- "время покажет, но..."
- "впереди много интересного"
- "следите за обновлениями"

**Fix:** replace with a concrete conclusion or delete. A post can end on its last substantive point — closing pathos is not required.

### A12. Hook formulas

AI has memorized blogger opening formulas and applies them every time.

**Markers:**
- "Я никогда не думал, что X. Пока не случилось Y..."
- "Вы наверняка слышали про X. Но мало кто знает, что Y..."
- "Что если я скажу вам, что..."
- "Представьте: ..."
- "Однажды я понял одну вещь..."
- "За последние N лет я сделал X. И вот что я понял..."

**Fix:** drop the formula, start with the content. If a hook is still needed — make it concrete (a number, an event, a name), not abstract.

---

## Section B. Structural AI patterns

The hardest thing to catch is not individual words but the structure of the text.

### B1. Symmetrical paragraphs

AI writes 3–5 paragraphs of roughly equal length (4–5 sentences each). A human author writes unevenly.

**Fix:** deliberately break the rhythm. One paragraph of two sentences, another of seven. Occasionally a single-sentence accent paragraph.

### B2. Mandatory summary at the end of every paragraph

AI closes paragraphs with conclusions: "Таким образом...", "Следовательно...", "В итоге...", "Подводя итог...". A human author summarizes where it's needed, not after every paragraph.

**Markers:** "таким образом", "следовательно", "в итоге", "подводя итог", "резюмируя", "иначе говоря", "одним словом", "если коротко"

**Fix:** remove the summarizing phrases; let the paragraph end on its last substantive point.

### B3. Duplicated intro and conclusion

AI opens the post with "what this will be about" and closes with "what this was about". Both parts paraphrase the main content.

**Fix:** compare the first and last paragraphs. If they say the same thing — delete one or rewrite it radically. In a blog post, no closing summary at all is better than a repeat of the intro.

### B4. List mania

AI formats everything as bullets, even where prose is needed. This isn't structure, it's a marker.

**Markers:**
- A mandatory list in every section
- Lists of 3–5 items, each item 1–2 sentences
- Lists inside lists
- Lists where the items are full sentences with subject and predicate (meaning it was prose forcibly broken into bullets)

**Fix:** if the items form a connected argument, rewrite as prose. Keep lists only where the elements are:
- Genuinely enumerable (steps, options, tools)
- Not causally linked to each other
- Each readable on its own, without the neighbors' context

### B5. Lists of exactly three

Almost every AI enumeration has three items: "X, Y и Z". Naturalness lies in irregularity.

**Fix:** sometimes leave two, sometimes four, sometimes a long dash-separated list.

### B6. Symmetrical coverage of items

If AI writes about N tools/methods/principles — each gets roughly the same amount of text. A human author covers one in detail and dismisses another in half a sentence.

**Fix:** deliberate asymmetry — it reflects the real importance of the items.

---

## Section C. Universal patterns (shared with the legal skill)

### C1. Vague attributions

AI cites faceless "experts" and "the majority".

**Markers:**
- "эксперты считают"
- "по мнению многих"
- "большинство специалистов сходятся во мнении"
- "в индустрии принято считать"
- "общепризнанным является"
- "статистика показывает" (no number, no source)
- "исследования говорят" (no link)

**Fix:** either name the specific author/study, or rephrase without the appeal to authority.

**Before:**
> Эксперты считают, что вайб-кодинг изменит индустрию разработки.

**After:**
> Карпатый назвал это "vibe coding" в феврале 2025 года. С тех пор термин ушёл в массы.

or (if you don't remember the source):

> Вайб-кодинг — это когда пишешь промпт, а ИИ генерит код. И с этим внезапно можно делать прод.

### C2. Explanatory repetition

AI says the same thing twice in different words, "for clarity".

**Before:**
> Агент работает автономно. Это значит, что он может выполнять задачи без вмешательства человека.

**After:**
> Агент работает автономно — без человека.

### C3. Explaining the obvious

AI explains what is already clear from context.

**Before:**
> Claude, который является большой языковой моделью от компании Anthropic, может писать код.

**After:**
> Claude умеет писать код.

A reader of an AI blog knows Claude is an LLM from Anthropic. If they don't — a separate sentence, not an inline insert.

### C4. Safe generalizations

Formally true, substantively empty phrases.

**Markers:**
- "существуют различные подходы"
- "есть множество способов"
- "вариантов масса"
- "решения зависят от конкретного случая"
- "всё индивидуально"
- "у каждого свой опыт"
- "однозначного ответа нет"
- "тема сложная и многогранная"

**Fix:** test every such phrase with the question "what exactly is being said here?". If nothing — delete or replace with specifics.

### C5. Synonym cycling

AI fears repetition and reaches for synonyms where a human author would calmly repeat.

**Before:**
> Агент работает быстро. Этот инструмент справляется за минуты. Данное решение экономит время.

**After:**
> Агент работает быстро — справляется за минуты.

### C6. Dash mania and decorative em dashes

AI uses the long dash as decoration. For a human author the dash is a working mark.

**Acceptable:** replacing the copula "это"/"является", a strong pause instead of a comma.

**Unacceptable:** three dashes in one paragraph for rhythm, especially when they sit in the same position in every sentence.

### C7. Excessive hedging

AI plays it safe:

- "может потенциально"
- "вероятно, что, возможно"
- "не исключено, что может быть"
- "в некоторых случаях иногда"

**Fix:** one hedge per unit of meaning, no more. In a blog it can often be removed entirely — the author's position sounds better without a hedge.

### C8. Passive voice

AI-Russian overuses passive constructions.

**Markers:**
- "были выявлены / установлены / определены"
- "рассматривается как"
- "понимается как"
- "может быть охарактеризовано"

**Fix:** find who performs the action and make the construction active.

**Before:**
> Агентами могут быть выполнены различные задачи.

**After:**
> Агенты могут выполнять разные задачи.

In a blog the passive is almost always worse than the active — replace boldly.

---

## Section D. Generative section — how to write well from the start

This is prevention, not cleanup. Write from these principles and there's less to clean later.

### D1. Open with specifics

The first sentence of the post is not a global statement but a concrete fact, observation or claim about the topic.

**Bad:**
> В современном мире AI-агенты становятся всё более популярными.

**Good:**
> Anthropic выкатил Claude 4.7. Главное изменение — Claude Code теперь умеет работать с Excel.

### D2. Specifics everywhere

Wherever you can put a number, a name, a date, a version — put it.

- "недавно" → "в марте 2026"
- "многие компании" → "Anthropic, OpenAI, Google"
- "значительный прирост" → "+40%"
- "несколько" → "три", "пять"
- "часто" → "в 70% случаев" (if you know) or delete

If you don't know the exact number — better to drop the evaluative word entirely than leave it vague.

### D3. Rhythmic variety

Short sentences mixed with long ones. Occasionally a very short one as an accent ("И вот тут начинается интересное.").

Check: every paragraph should have at least one very short sentence (3–7 words) and one longer one.

### D4. A position of your own

In a blog the author is entitled to a position. Not necessarily "я считаю" — it can come through:
- "Тут есть проблема: ..."
- "Эта штука переоценена."
- "Аргумент звучит убедительно, но..."
- "На практике это не работает, потому что..."
- "Решение прагматичное, но кривое."

AI is afraid to take a position. A human author isn't.

### D5. Appropriate conversational turns (in moderation)

In blog text you may use (but not in every paragraph):
- "Беда в том, что..."
- "Получается, что..."
- "Главное здесь — ..."
- "Замысел понятен."
- "Это работает так:"
- "На пальцах:"
- "По факту..."

The norm is 2–3 per post, not per paragraph. Overdoing it makes the text "bloggerish" in the worst sense.

### D6. Don't explain the obvious

Trust the reader. If they're reading a post about AI agents, they know what an LLM is. If the post is about vibe coding, they know Karpathy. Don't insert an explanation at every mention.

### D7. Acknowledge complexity

Where there's nuance — mention it. AI often writes as if everything were unambiguous. A human author honestly says "тут спорный момент", "это работает не всегда", "у меня нет ответа".

### D8. Concrete examples instead of abstractions

Back every abstract claim with an example. Not "AI-агенты экономят время" but "агент закрыл 30 заявок в Jira за час, что у меня заняло бы три дня".

---

## Section E. What NOT to do (typical humanization mistakes)

### Basic rules

1. **Don't turn it into TikTok copy.** The goal is a lively blog style, not a 7-word post with emojis.
2. **Don't strip all structure.** Headings and lists (where appropriate) are fine.
3. **Don't make every sentence short.** Hemingway style in a blog is also a marker — not of AI, but of imitation.
4. **Don't insert "я" into every sentence.** "Я думаю", "я считаю", "я заметил" — annoying after the third time.
5. **Don't use slang where it doesn't fit.** vc.ru is not a school chat.
6. **Don't throw out technical terms.** "AI-агент" stays "AI-агент", not "помощник на ИИ".

### Humanization anti-patterns (bad edits)

**Anti-pattern 1: Swapping in a filler synonym.**

- "является" → "представляет собой" — same AI
- "следует отметить" → "стоит сказать" / "важно подчеркнуть" — filler synonyms
- "данный" → "указанный" / "рассматриваемый" — same bureaucratese
- "осуществляется" → "производится" / "реализуется" — just relocating the marker

**Correct:** remove the construction entirely or rephrase with an active verb.

**Anti-pattern 2: Replacing passive with passive.**

- "устанавливается" → "является установленным" — a different passive
- "применяется" → "находит применение" — worse than the original

**Correct:** find the subject and make the construction active.

**Anti-pattern 3: Imitating a human author with a single device.**

- "Беда в том, что..." everywhere — three times per post = a new marker
- A short accent sentence at the end of every paragraph — a recognizable pattern
- Dash inserts everywhere — looks like a mannerism, not living rhythm

**Correct:** variety of techniques, not repetition of one "humanizing" tell.

**Anti-pattern 4: Cosmetics without structural editing.**

Removing "следует отметить" from every paragraph — but leaving all paragraphs the same length with a summary at the end. The vocabulary is clean, the structure is AI.

**Correct:** after cleaning the words, run the structure audit (B1–B6).

**Anti-pattern 5: Imitating a Telegram blogger.**

- "короче" everywhere
- Ending sentences with "ну вы поняли"
- "лол", "кек", "топчик" every two paragraphs

In blog content this is no longer humanization but imitation of a specific genre. Don't do it if the task is a neutral blog style.

**Anti-pattern 6: Switching to emotion.**

Replacing AI inflation with your own emotional inflation: "это просто огонь", "это прям бомба". That's the other extreme.

**Correct:** specifics instead of emotion. "Это огонь" → "это сократило время с 8 часов до 30 минут".

### Protection against over-humanizing (reverse counters)

| Marker | Acceptable | If more |
|---|---|---|
| conversational turns ("беда в том", "короче", "получается") | 2–3 per post | roll some back |
| sentences shorter than 5 words | up to 30% of all sentences | add connected reasoning |
| "я" / "мне кажется" / "по моему мнению" | in moderation, not in every sentence | make impersonal or remove |
| emojis | on request / by context, not as decoration | remove |
| exclamation marks | 0–2 per post | remove extras |
| rhetorical questions | 1–2 per post | remove extras |
| slang ("топ", "огонь", "база") | 0 in a neutral blog | replace with neutral |

Sign of over-humanizing: the post sounds like a schoolkid's Telegram channel rather than a vc.ru piece.

---

## Final audit (mandatory step)

### Counters (go through the text and count)

| Marker | Acceptable | If more |
|---|---|---|
| "следует отметить" / "стоит отметить" / "хочется отметить" | 0 | remove all |
| "является" | 1–2 per medium-length post | replace with a dash or a verb |
| "данный" | 0 | "этот" or delete |
| "осуществляется" / "производится" | 0 | a concrete verb |
| openers "в современном мире / эпохе" | 0 | delete |
| "важно понимать" / "запомните" / "главное" (mentor tone) | 0–1 per post | remove |
| summarizing paragraph endings ("таким образом", "в итоге") | 0–1 per post | remove extras |
| lists of exactly 3 items | no more than half | break the rhythm: 2 or 4 |
| paragraphs of equal length (±1 sentence) | no more than 2 in a row | split or merge |
| safe generalizations ("различные подходы", "есть много способов") | 0 | replace with specifics |
| emotional epithets ("революционный", "впечатляющий", "потрясающий") | 0–1 per post | replace with specifics |
| passive constructions | no more than 20% of sentences | make active |
| lists/bullets | only if the elements are genuinely enumerable | rewrite as prose |

### Structural checks

1. **Is the first paragraph specifics or pathos?** If "В современном мире..." — rewrite from a fact.
2. **Duplicated intro and ending:** compare — if they say the same thing, delete one.
3. **Sentence rhythm:** is there at least one short sentence (3–7 words) in every paragraph?
4. **Specifics:** are there numbers, names, dates, versions in the text? If everything is at the level of general words — add specifics.
5. **Symmetry of coverage:** if N points are listed, does each get the same volume? If yes — make it deliberately asymmetrical.
6. **Ending:** does the post close with a grand phrase about "the future" or "prospects"? If yes — remove or replace with a concrete conclusion.

### Protection against the reverse problem

Run the reverse counters (Section E — "Protection against over-humanizing"). If there's too much conversational tone, "я" or emotion — roll back part of the edits.

### Final check

Read the post aloud. Signs of finished text:
- No "announcer's voice"
- Doesn't sound like a LinkedIn motivator
- Doesn't sound like a schoolkid's TikTok copy
- Has concrete facts, not only generalizations
- Has the author's position where appropriate
- Uneven rhythm — short and long sentences mixed

---

## Worked example

### Before (AI draft):

> В современную эпоху, когда искусственный интеллект развивается стремительными темпами, всё больше компаний задумываются о внедрении AI-агентов в свои бизнес-процессы. Важно понимать, что AI-агенты представляют собой не просто инструмент автоматизации, а революционную технологию, которая открывает новые горизонты для бизнеса.
>
> Существует несколько подходов к внедрению AI-агентов. Эксперты выделяют три основных направления: автоматизация рутинных задач, оптимизация процессов принятия решений и улучшение клиентского опыта. Каждое из этих направлений имеет свои особенности и требует индивидуального подхода.
>
> Таким образом, AI-агенты — это технология, которая меняет правила игры. Будущее уже здесь, и компании, которые не успеют адаптироваться, рискуют остаться позади.

**What's wrong:**
- "В современную эпоху..." — A1
- "Важно понимать" — A3
- "Представляют собой" — A6 / anti-pattern (a synonym for "является")
- "Революционную технологию", "открывает новые горизонты" — A7, A11
- "Существует несколько подходов" — C4 (safe generalization)
- "Эксперты выделяют" — C1 (vague attribution)
- "Три основных направления" — B5 (rule of three)
- "Каждое имеет свои особенности и требует индивидуального подхода" — C4
- "Таким образом" — B2
- "Будущее уже здесь, рискуют остаться позади" — A11 (upbeat ending)
- All three paragraphs the same length — B1

### After:

> AI-агентов сейчас внедряют все подряд. Большинство — впустую.
>
> Реальных сценариев, где агент окупается, всего три. Первый — рутина с чёткими правилами: разбор писем, обновление CRM, ответы на типовые вопросы. Это работает. Второй — задачи, где нужен поиск по большому объёму данных и быстрый ответ: агент копает базу знаний, человек принимает решение. Тоже работает. Третий — клиентская поддержка первой линии. Тут уже сложнее, и провалов больше, чем успехов: агент не понимает контекст, бесит клиентов, его приходится дублировать живым оператором.
>
> Всё остальное — маркетинг. Если кто-то продаёт "AI-агента для стратегического планирования" — это либо обёртка над промптом в ChatGPT, либо чат-бот с тремя сценариями. Платить за это бессмысленно.

**What was done:**
- Removed the grandiose opener — the post opens with a concrete claim and a position
- Removed the mentor tone ("важно понимать") and the epithets ("революционная", "новые горизонты")
- "Эксперты выделяют" replaced with the author's own position
- "Три основных направления" — formally still three, but covered asymmetrically (first and second briefly, third with nuance)
- Paragraphs of different length: 2 sentences / 5 / 3
- Concrete examples instead of generalizations (CRM, knowledge bases, first-line support)
- Substantive ending, no "будущее уже здесь"
- The author's position and judgment appeared ("работает", "бесит клиентов", "бессмысленно")

---

## Cheat sheet (top edits)

**Always clean:**

1. "В современном мире / эпоху / в условиях X" → delete, start with a fact
2. "Важно понимать / запомните / главное" → delete
3. "Является X" → "X" / "— X" / rephrase
4. "Представляет собой" → same thing, delete or rephrase
5. "Данный" → "этот" or delete
6. "Осуществляется" / "функционирование" / "механизм" → a concrete verb
7. "Эксперты считают" / "большинство" → a specific source or your own position
8. "Революционный" / "впечатляющий" / "меняет всё" → specifics
9. "Таким образом" / "в итоге" at the end of a paragraph → delete
10. "Будущее уже здесь" / "открывает горизонты" → a concrete conclusion or delete
11. "Существуют различные подходы" → name which ones
12. Prose lists → rewrite as prose

**Never do:**

1. "Является" → "представляет собой" (filler synonym, same AI)
2. "Беда в том, что..." everywhere (repeating a device = a new marker)
3. Replacing AI inflation with your own ("это огонь", "это бомба")

---

## Versioning

- **v1.0.0** (current) — first version. Universal skill for blog content (Telegram, vc.ru, Habr and similar). Neutral voice. Adapted from `humanizer-ru-legal` v1.2.0 + blog-genre specifics (LinkedIn formulas, mentor tone, emotional inflation, list mania, hook formulas, upbeat ending).
