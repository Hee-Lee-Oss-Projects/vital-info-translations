<!--
  Deliverable: Arabic translation of vetted dengue prevention guidance
  Project: vital-info-translations  ·  Task: vit-dengue-prevention-arabic
  Status: DRAFT — NOT FOR FIELD DISTRIBUTION until the two human-held gates below are closed.
  Revision: 2026-07-24 — coverage expanded to the full source fact sheet (Overview, global
  burden figures, full Transmission section, hospitalization, WHO response), English
  source-equivalent and glossary updated to match. See §8 for the revision log.
-->

# حُمّى الضَّنْك وحُمّى الضنك الوخيمة: الوقاية والمكافحة — إرشادات للعاملين الصحّيين المجتمعيين
# Dengue & Severe Dengue — Prevention Guidance for Community Health Workers (Arabic)

> **⚠️ حالة الوثيقة / Document status: DRAFT — DELIVERED, NOT YET CLEARED.**
> This is a complete translation draft delivered for review. It is **not** field-ready and
> **must not be distributed** until BOTH gates below are closed and recorded in the PR:
>
> 1. **Qualified-reviewer sign-off (PENDING).** A qualified Arabic-speaking reviewer with
>    health-translation competence, **independent of the drafter**, must verify accuracy, medical
>    terminology, and safety messaging (see *Reviewer handoff*, §7). Because this draft contains
>    **safety-critical "when to seek care" and medication content**, a **second independent
>    reviewer** is required per the project's safety-critical rule (PLAN.md).
> 2. **License & source verification (PENDING / BLOCKING).** The exact current reuse terms of the
>    specific WHO source must be confirmed in writing and recorded on the source allow-list entry
>    (which is still `reviewStatus: provisional`), and the translated text must be **reconciled
>    line-by-line against the live WHO source**. A live fetch of the source page was **attempted in
>    the 2026-07-24 revision session and was not permitted** by the execution environment, so this
>    gate remains open (see *Provenance*, §1, and *Self-check flags*, §6).
>
> The drafting agent **cannot** self-certify either gate. Both are recorded as open below.

---

## 1. Provenance / المصدر والإسناد

| Field | Value |
|---|---|
| **Source (canonical)** | World Health Organization (WHO) — *Dengue and severe dengue* fact sheet |
| **Source URL** | https://www.who.int/news-room/fact-sheets/detail/dengue-and-severe-dengue |
| **Source version / date** | ⚠️ TO VERIFY against live page (the page's "fact sheet updated" date was not captured — no live fetch) |
| **Retrieval date** | Not retrieved live. Drafted 2026-06-28 and revised 2026-07-24 from established WHO dengue fact-sheet content; live fetch attempted 2026-07-24 and **not permitted** by the environment |
| **Allow-list entry** | `who-publications` in `sources/allow-list.yaml` — currently `status: included`, **`reviewStatus: provisional`** (hard gate not yet passed: no live capture, `sha256: null`, `archiveUrl: null`) |
| **License (asserted, TO VERIFY)** | WHO content is typically **CC BY-NC-SA 3.0 IGO** (Attribution–NonCommercial–ShareAlike 3.0 IGO) — **not** CC-BY. Web fact sheets may carry the WHO website terms of use; **confirm the exact terms for this specific page before delivery.** |
| **License URL** | https://creativecommons.org/licenses/by-nc-sa/3.0/igo/ · WHO terms: https://www.who.int/about/policies/publishing/copyright |
| **Derivatives / translation permitted?** | CC BY-NC-SA 3.0 IGO permits translation **with** attribution, the ShareAlike condition, the non-commercial restriction, and the **mandatory WHO translation disclaimer**. ⚠️ Confirm this applies to the specific source. |
| **Output license (this translation)** | Inherits **CC BY-NC-SA 3.0 IGO** (source-compatible). **NOT relicensed as CC-BY.** |
| **Translator** | Claude agent (draft) + qualified human reviewer (PENDING) |
| **Reviewer / sign-off** | PENDING (see §7) |

### 1.1 License verification — what is verified vs. human-held

Following the project's split of license verification into *automatable-verified* and *held-human*
steps, the status of each step is recorded explicitly:

| # | Step | Automatable? | Status |
|---|---|---|---|
| 1 | Source is on the project allow-list and not `excluded` | yes | **✅ verified** — `who-publications`, `status: included` |
| 2 | Allow-list entry records translation/derivatives as permitted | yes | **✅ verified** — `translationAllowed: yes`, `derivativesAllowed: yes` |
| 3 | Output license is source-compatible and **not** widened to CC-BY | yes | **✅ verified** — output recorded as CC BY-NC-SA 3.0 IGO; `isCcBy: false` respected |
| 4 | Mandatory translation disclaimer present verbatim (EN) + rendered (AR) | yes | **✅ verified** — §2, matches `disclaimerText` in the allow-list |
| 5 | Required attribution string present (EN + AR) | yes | **✅ verified** — §2 |
| 6 | Live fetch of the specific source page; capture license bytes; record sha256 + archive URL | **no — held human / blocked** | **❌ OPEN** — fetch attempted 2026-07-24, not permitted |
| 7 | Confirm the *specific page's* current terms in writing; promote allow-list entry to `reviewStatus: confirmed` | **no — held human** | **❌ OPEN** |
| 8 | Confirm the exact required disclaimer wording against current WHO terms | **no — held human** | **❌ OPEN** |
| 9 | Line-by-line reconciliation of this text against the live source (figures, dates, wording) | **no — held human** | **❌ OPEN** |

> **Why no live fetch:** web fetch was unavailable in the original drafting session, and in the
> 2026-07-24 revision session the fetch was attempted but the environment did not grant it. Per
> project policy ("if unclear, don't translate"; source-integrity verification required), the
> **license/compliance reviewer must fetch the live WHO page, snapshot/hash its license text, record
> version + retrieval date, and reconcile the English source text in §4** before this deliverable is
> cleared. Steps 1–5 above are recorded as verified; they do **not** substitute for steps 6–9.

---

## 2. Attribution & mandatory translation disclaimer

**Required WHO translation disclaimer (English — reproduce verbatim):**

> *This translation was not created by the World Health Organization (WHO). WHO is not responsible
> for the content or accuracy of this translation. The original English edition shall be the
> binding and authentic edition.*

**إخلاء المسؤولية عن الترجمة (بالعربية):**

> *لم تُعِدّ منظمةُ الصحة العالمية (WHO) هذه الترجمة. والمنظمةُ غير مسؤولة عن محتوى هذه الترجمة أو
> دقّتها. والنسخةُ الإنجليزية الأصلية هي النسخةُ المُلزِمة وذاتُ الحُجِّية.*

**Attribution / الإسناد:** Adapted and translated from the World Health Organization fact sheet
*"Dengue and severe dengue"* (© WHO), licensed (to be confirmed) under CC BY-NC-SA 3.0 IGO.
There is no suggestion that WHO endorses this translation, any organization, product, or service.

**مقتبَس ومترجَم عن صحيفة وقائع منظمة الصحة العالمية «حُمّى الضنك وحُمّى الضنك الوخيمة» (© منظمة
الصحة العالمية)، بموجب رخصة CC BY-NC-SA 3.0 IGO (قيد التحقّق). ولا يُفهَم من ذلك أيُّ تأييد من
المنظمة لهذه الترجمة أو لأيّ جهة أو مُنتَج أو خدمة.**

**Scope note / تنبيه بشأن النطاق:** هذه إرشادات مرجعية عالمية، ولا تُغني عن استشارة مختصٍّ صحّي
مؤهَّل ولا عن الإرشادات الصادرة عن السلطة الصحّية الوطنية، وهي المرجع المُلزِم عملياً في كلّ بلد.

---

## 3. الترجمة العربية (النصّ الأساسي / primary deliverable)

> اتجاه النص: من اليمين إلى اليسار (RTL).

### الحقائق الرئيسية

- حُمّى الضَّنْك عدوى فيروسية تنتقل إلى الإنسان عن طريق لدغ البعوض المُصاب، وخاصةً بعوضة **الزاعجة المصرية (*Aedes aegypti*)**، وكذلك بدرجة أقل **الزاعجة المُرقّطة (*Aedes albopictus*)**.
- نحو **نصف سكان العالم** معرَّضون اليوم لخطر الإصابة بحُمّى الضنك، ويُقدَّر عدد الإصابات بنحو **100 إلى 400 مليون إصابة سنوياً**.
- تنتشر حُمّى الضنك في المناخات **المدارية وشبه المدارية** حول العالم، وخاصةً في المناطق **الحضرية وشبه الحضرية**.
- كثير من حالات العدوى لا تُسبِّب أعراضاً أو تكون خفيفة، ويتعافى معظم المصابين خلال **أسبوع إلى أسبوعين**؛ غير أنّ الفيروس قد يُسبِّب أحياناً مرضاً أشدّ وطأة، بل والوفاة.
- قد تتطوّر لدى بعض المرضى حالةٌ **وخيمة (حُمّى الضنك الوخيمة)** تستلزم رعايةً في المستشفى، وقد تكون مميتة.
- **لا يوجد علاجٌ نوعيٌّ** لحُمّى الضنك؛ غير أنّ الكشف المبكِّر والحصول على الرعاية الطبية المناسبة يقلّلان كثيراً من معدّل الوفيات في الحالات الوخيمة.
- تعتمد الوقاية والمكافحة بصورة أساسية على **مكافحة النواقل (البعوض)**.

### نظرة عامة

حُمّى الضَّنْك — وتُسمّى أحياناً **«حُمّى تكسير العظام»** (*break-bone fever*) — عدوى فيروسية تنتقل
من البعوض إلى الإنسان، وهي أكثر شيوعاً في المناخات المدارية وشبه المدارية. ولا تظهر أعراضٌ على
معظم المصابين بها؛ أمّا من تظهر عليهم الأعراض فأكثرها شيوعاً: الحُمّى المرتفعة، والصداع، وآلام
الجسم، والغثيان، والطفح الجلدي. ويتعافى معظم المرضى خلال أسبوع إلى أسبوعين. غير أنّ بعضهم يُصاب
بـ**حُمّى الضنك الوخيمة** التي تستلزم الرعاية في المستشفى، وقد تكون مميتة في الحالات الشديدة.

ويمكنك تقليل خطر إصابتك بحُمّى الضنك عن طريق **تجنُّب لدغ البعوض**، ولا سيّما **في أثناء النهار**.
ولا يوجد حتى الآن علاجٌ نوعيٌّ للمرض؛ وتقوم الرعاية على **تسكين الألم ودعم المريض**.

### كيف تنتقل العدوى

تتسبّب في المرض فيروسات الضنك (DENV)، ولها أربعة أنماط مصلية (DENV‑1 إلى DENV‑4). ويمنح التعافي من
أحد الأنماط مناعةً مدى الحياة تجاه ذلك النمط تحديداً، لكنّ المناعة تجاه الأنماط الأخرى تكون جزئيةً
ومؤقتة؛ ولذلك فإنّ الإصابة لاحقاً بنمطٍ آخر **تزيد من خطر الإصابة بالضنك الوخيم**.

**أولاً: انتقال العدوى من البعوض إلى الإنسان**
- ينتقل الفيروس إلى الإنسان عن طريق لدغ إناث البعوض المُصابة، وفي المقام الأول **الزاعجة المصرية (*Aedes aegypti*)**. وقد تنقل الفيروس أيضاً أنواعٌ أخرى من جنس *Aedes*، ومنها **الزاعجة المُرقّطة (*Aedes albopictus*)**.
- بعد أن تتغذّى البعوضة على دم شخصٍ مصاب بفيروس الضنك (DENV)، يتكاثر الفيروس في **المِعى المتوسّط** للبعوضة، ثم ينتشر إلى أنسجة أخرى ومنها **الغدد اللعابية**.
- وتُسمّى المدّة الفاصلة بين ابتلاع البعوضة للفيروس وقدرتها على نقله إلى مضيفٍ جديد **فترة الحضانة خارج الجسم (Extrinsic Incubation Period — EIP)**، وتبلغ نحو **8 إلى 12 يوماً** عندما تتراوح درجة حرارة الجو بين **25 و28 درجة مئوية**.
- وتنشط هذه البعوضة في **النهار**، وتزداد لدغاتها في الصباح الباكر وقبل غروب الشمس.
- ويتكاثر هذا البعوض في **تجمّعات صغيرة من المياه الراكدة** (الأوعية المنزلية، والإطارات المستعملة، وغيرها).

**ثانياً: انتقال العدوى من الإنسان إلى البعوض**
- يمكن أن تُصاب البعوضة عند لدغ شخصٍ يحمل فيروس الضنك في دمه (**حالة فيروسيّة الدم / viremic**).
- وقد يكون هذا الشخص مصاباً بعدوى ظاهرة الأعراض، أو لم تظهر عليه الأعراض بعد (**ما قبل ظهور الأعراض**)، أو لا تظهر عليه أيّ علامات مرض (**عديم الأعراض**).
- ويمكن أن يحدث هذا الانتقال **قبل ظهور الأعراض بيومين** وحتى **يومين بعد زوال الحُمّى**.

**ثالثاً: الانتقال من الأمّ إلى الجنين**
- ينتقل الفيروس بين البشر أساساً عن طريق البعوض الناقل، غير أنّ هناك أدلّةً على إمكان انتقاله من **الأمّ الحامل إلى جنينها**.
- وقد يترتّب على ذلك **ولادة مبكِّرة**، و**انخفاض الوزن عند الولادة**، و**ضائقة جنينية**.

**رابعاً: طرق انتقال أخرى**
- سُجِّلت حالات نادرة للانتقال عن طريق **منتجات الدم**، و**التبرّع بالأعضاء**، و**عمليات نقل الدم**.

### العلامات والأعراض

- لا تظهر أعراضٌ على معظم المصابين، أو تكون أعراضهم خفيفة، ويتعافون خلال أسبوع إلى أسبوعين. وفي حالات نادرة قد تكون حُمّى الضنك وخيمةً وتؤدّي إلى الوفاة.
- وعند ظهور الأعراض، تبدأ عادةً بعد **فترة حضانة تتراوح بين 4 و10 أيام** من الإصابة، وتستمرّ عادةً من **يومين إلى سبعة أيام**.
- يُشتبَه بحُمّى الضنك عند وجود **حُمّى مرتفعة (تصل إلى 40 درجة مئوية / 104 درجة فهرنهايت)** مصحوبة باثنين أو أكثر من الأعراض التالية:
  - صداع شديد؛
  - ألم خلف العينين (ألم خلف المُقلة)؛
  - آلام في العضلات والمفاصل؛
  - غثيان؛
  - قيء؛
  - تورّم الغدد (اعتلال العُقَد اللمفية)؛
  - طفح جلدي.
- ومَن يُصاب بالعدوى **للمرّة الثانية** يكون أكثر عُرضةً للإصابة بحُمّى الضنك الوخيمة.

### العلامات التحذيرية للضنك الوخيم — حالة طارئة

غالباً ما تظهر العلامات التحذيرية **بعد زوال الحُمّى** (عادةً بين اليوم الثالث والسابع من بدء المرض). **اطلب الرعاية الطبية فوراً** عند ظهور أيٍّ ممّا يلي:

- ألم شديد في البطن؛
- قيء مستمرّ؛
- تنفّس سريع؛
- نزيف من اللثة أو الأنف؛
- تعب شديد؛
- تململ وقلق (هياج)؛
- وجود دم في القيء أو البراز؛
- عطش شديد؛
- شحوب الجلد وبرودته؛
- شعور بالضعف الشديد.

> **الضنك الوخيم حالةٌ طبيةٌ طارئة قد تكون مميتة. لا تنتظر — توجَّه إلى أقرب مرفق صحّي على الفور.**

### التشخيص والرعاية والعلاج

- **لا يوجد علاجٌ نوعيٌّ مضادٌّ للفيروس.** تهدف الرعاية إلى **تخفيف الأعراض المؤلمة** ودعم المريض.
- يمكن علاج **معظم حالات حُمّى الضنك في المنزل** باستخدام مسكّنات الألم.
- ينبغي **الراحة** و**شرب كميات كافية من السوائل**.
- يمكن استخدام **الباراسيتامول (الأسيتامينوفين)** لخفض الحُمّى وتسكين الألم.
- **تجنّب** مضادات الالتهاب غير الستيرويدية مثل **الإيبوبروفين** و**الأسبرين**، لأنّها قد **تزيد من خطر النزيف**.
- راقِب ظهور العلامات التحذيرية، واطلب الرعاية الطبية فوراً عند ظهور أيٍّ منها.
- وغالباً ما يحتاج المصابون بـ**حُمّى الضنك الوخيمة** إلى **الرعاية في المستشفى**.

> ⚠️ ملاحظة للمراجِع: المقطع المتعلّق بالأدوية وتجنُّب مضادات الالتهاب غير الستيرويدية مقطعٌ **حسّاس
> من ناحية السلامة**؛ يجب التحقّق من صياغته بدقّة (راجع §6 و§7).

### اللقاحات

- توجد **لقاحاتٌ ضدّ حُمّى الضنك**، وقد أدخلت بعض البلدان التطعيم ضمن استراتيجيات المكافحة لديها.
- إلّا أنّ التوصيات بشأن اللقاحات المتاحة والفئات المؤهَّلة وشروط الاستخدام **تتغيّر وتختلف بين البلدان**.
- اتّبِع دائماً **توصيات السلطة الصحّية الوطنية ومنظمة الصحة العالمية السارية** بشأن التطعيم. ولا يُغني اللقاح عن تدابير مكافحة البعوض والوقاية الشخصية.

### الوقاية والمكافحة (الجزء الأساسي)

أفضل وسيلة للوقاية من حُمّى الضنك هي **تجنُّب لدغ البعوض** و**القضاء على أماكن تكاثره**. وبما أنّ البعوض الناقل ينشط نهاراً، فإنّ الحماية مطلوبةٌ في أثناء النهار كذلك.

**أولاً: الحماية الشخصية من اللدغ**
- ارتدِ ملابس تُغطّي أكبر قدر ممكن من الجسم.
- استخدم **الناموسيات** أثناء النوم نهاراً، ويُفضَّل أن تكون **معالَجة بالمبيدات الحشرية**، وخاصةً لحماية الرُّضّع والأطفال الصغار والحوامل والمرضى.
- ركّب **شبكاتٍ سلكية** على النوافذ والأبواب.
- استخدم **طاردات الحشرات** على الجلد المكشوف أو الملابس (مثل المستحضرات المحتوية على **DEET** أو **الإيكاريدين/البيكاريدين (Picaridin)** أو **IR3535**)، مع اتّباع تعليمات المُلصَق بدقّة.
- يمكن استخدام **اللفائف الطاردة للبعوض (الحلزونية) والمبخِّرات** في الأماكن المغلقة.

**ثانياً (الأهمّ): القضاء على أماكن تكاثر البعوض**
- امنع وصول البعوض إلى أماكن وضع البيض عن طريق **إدارة البيئة وتعديلها**.
- **غطِّ** أوعية تخزين المياه المنزلية، و**أفرِغها ونظّفها أسبوعياً**.
- تخلَّص من أيّ أوعية أو أغراض تجمع المياه الراكدة أو اقلبها (الإطارات المستعملة، والدِّلاء، والأواني، وصحون أصص النباتات).
- تخلَّص من **النفايات الصلبة** بطريقة سليمة حتى لا تتجمّع فيها المياه.
- يمكن إضافة **مبيدات حشرية مناسبة (مبيدات اليرقات)** إلى خزّانات المياه الخارجية التي يتعذَّر تغطيتها.

**ثالثاً: التدابير المجتمعية**
- شارِك في **حملات النظافة** والتوعية المجتمعية لإزالة أماكن تكاثر البعوض.
- عزِّز **مشاركة المجتمع وتعبئته** لضمان استدامة مكافحة النواقل.
- في أثناء الفاشيات، قد تشمل تدابيرُ الطوارئ **الرشّ الجوّي (الرذاذي) للمبيدات الحشرية** للحدّ من أعداد البعوض البالغ.
- ادعم **الترصُّد النشِط للنواقل ومراقبتها** للكشف المبكّر عن المخاطر.

> **متى تطلب الرعاية:** يجب على كلّ من تظهر عليه علاماتٌ تحذيرية للضنك الوخيم أن يطلب الرعاية الطبية
> **فوراً**. وعند انتشار حُمّى الضنك في منطقتك، توجَّه مبكّراً إلى المرفق الصحّي عند الإصابة بالحُمّى.

### استجابة منظمة الصحة العالمية

تتصدّى منظمة الصحة العالمية لحُمّى الضنك بوسائل منها:
- **دعم البلدان في تأكيد الفاشيات** عبر شبكة مختبراتها المتعاونة؛
- تقديم **الدعم التقني والإرشاد** لإدارة الفاشيات والتصدّي لها؛
- مساعدة البلدان على **تحسين نظم الإبلاغ** لديها؛
- توفير **التدريب وبناء القدرات**؛
- وضع **استراتيجيات قائمة على الأدلّة**، بما في ذلك في إطار **المبادرة العالمية لمكافحة الفيروسات المنقولة بالمفصليات (Global Arbovirus Initiative)**.

---

## 4. English source-equivalent text (for reviewer verification)

> Provided so the reviewer can verify the Arabic against the source. ⚠️ **This English text must be
> reconciled against the live WHO fact sheet before sign-off** — it reflects established WHO dengue
> fact-sheet content but was not captured by live fetch.

**Key facts.** Dengue is a viral infection spread to humans through the bite of infected mosquitoes,
chiefly *Aedes aegypti* (and, to a lesser extent, *Aedes albopictus*). About **half the world's
population** is now at risk of dengue, with an estimated **100–400 million infections** each year.
Dengue is found in tropical and subtropical climates worldwide, mostly in **urban and semi-urban
areas**. Many infections are asymptomatic or mild and most people recover in **1–2 weeks**; the
virus can occasionally cause more severe illness and death. Some develop **severe dengue**, which
needs hospital care and can be fatal. **There is no specific treatment**; early detection and access
to proper medical care greatly lower fatality of severe dengue. Prevention and control depend mainly
on **mosquito (vector) control**.

**Overview.** Dengue (sometimes called "break-bone fever") is a viral infection that spreads from
mosquitoes to people. It is more common in tropical and subtropical climates. Most people who get
dengue **have no symptoms**; for those who do, the most common are high fever, headache, body aches,
nausea and rash. Most recover in 1–2 weeks. Some develop **severe dengue** needing hospital care,
and in severe cases dengue can be fatal. You can lower your risk by **avoiding mosquito bites**,
especially during the day. There is no specific treatment; care focuses on **treating pain
symptoms**.

**Transmission.** Caused by dengue virus (DENV), with four serotypes (DENV-1 to DENV-4). Recovery
from one serotype gives lifelong immunity to that serotype but only partial, temporary protection
against the others; a later infection with a different serotype **increases the risk of severe
dengue**.
*Mosquito-to-human:* the virus is transmitted by the bite of infected female mosquitoes, primarily
*Aedes aegypti*; other *Aedes* species such as *Aedes albopictus* can also transmit it. After
feeding on the blood of a DENV-infected person, the virus replicates in the mosquito **midgut**
before disseminating to other tissues including the **salivary glands**. The time from ingesting the
virus to transmitting it to a new host is the **extrinsic incubation period (EIP)** — about **8–12
days** at ambient temperatures of **25–28 °C**. *Aedes aegypti* **bites during the daytime** (peaking
in early morning and before dusk) and breeds in **small collections of standing water** (household
containers, used tires, etc.).
*Human-to-mosquito:* mosquitoes can be infected by biting a **viremic** person — someone with
symptomatic infection, someone not yet symptomatic (pre-symptomatic), or someone with no signs of
illness (asymptomatic). This can occur up to **2 days before** symptoms begin and up to **2 days
after** the fever resolves.
*Maternal transmission:* the primary human-to-human route is via mosquito vectors, but there is
evidence of possible transmission from a **pregnant person to their baby**, with infants at risk of
**pre-term birth, low birthweight, and fetal distress**.
*Other routes:* rare cases have been recorded via **blood products, organ donation, and
transfusions**.

**Signs and symptoms.** Most people are asymptomatic or mildly ill and recover in 1–2 weeks; rarely,
dengue is severe and can be fatal. When symptoms occur, they appear after a **4–10 day incubation**
and last **2–7 days**, and include **high fever (40 °C / 104 °F)** plus two or more of: severe
headache, pain behind the eyes, muscle and joint pains, nausea, vomiting, swollen glands, rash.
People infected a **second time** are at greater risk of severe dengue.

**Severe dengue — warning signs (emergency).** Often appear **after the fever subsides** (typically
days 3–7 of illness). **Seek care immediately** for: severe abdominal pain; persistent vomiting;
rapid breathing; bleeding gums or nose; severe fatigue; restlessness; blood in vomit or stool;
extreme thirst; pale, cold skin; weakness. **Severe dengue is a life-threatening medical
emergency — go to the nearest health facility at once.**

**Diagnosis, care and treatment.** No specific antiviral treatment; care is supportive and aims to
**treat pain symptoms**. Most dengue cases can be managed **at home with pain medicine**: **rest**,
adequate **fluids**, and **paracetamol (acetaminophen)** for fever and pain. **Avoid NSAIDs such as
ibuprofen and aspirin**, which can increase bleeding risk. Watch for warning signs and seek care
immediately if any appear. People with **severe dengue often need hospital care**.

**Vaccines.** Dengue vaccines exist and some countries have introduced vaccination as part of
control strategies, but recommendations on available vaccines, use, and eligible groups **vary by
country and change over time**. Always follow current **national health authority and WHO**
guidance. Vaccination does not replace mosquito control and personal protection.

**Prevention and control.** The best prevention is to **avoid mosquito bites** and **eliminate
breeding sites**; because the vector bites in daytime, protection is needed during the day.
*Personal protection:* wear covering clothing; use mosquito nets (ideally insecticide-treated),
especially for infants, young children, pregnant people, and the sick, when sleeping by day; fit
window/door screens; apply repellents (e.g., DEET, picaridin/icaridin, IR3535) to exposed
skin/clothing per label; use coils and vaporizers indoors. *Eliminate breeding sites (most
important):* prevent mosquitoes from accessing egg-laying habitats through **environmental
management and modification**; cover, empty, and clean water-storage containers **weekly**; remove
or overturn items that collect standing water (used tires, buckets, pots, plant-pot saucers);
dispose of **solid waste** properly; apply appropriate **insecticides/larvicides** to outdoor water
containers that cannot be covered. *Community measures:* join clean-up and awareness campaigns;
strengthen **community engagement and mobilization** for sustained vector control; during outbreaks,
emergency control may include **space spraying** of insecticides; maintain **active vector
surveillance and monitoring**. *When to seek care:* anyone with severe-dengue warning signs must
seek care **immediately**.

**WHO response.** WHO responds to dengue by supporting countries to confirm outbreaks through its
collaborating laboratory network; providing technical support and guidance for outbreak management;
helping countries improve reporting systems; providing training and capacity building; and
developing evidence-based strategies, including through the **Global Arbovirus Initiative**.

---

## 5. Preserved-terminology glossary (EN ↔ AR)

| English | العربية | Notes |
|---|---|---|
| Dengue / severe dengue | حُمّى الضَّنْك / حُمّى الضنك الوخيمة | |
| Break-bone fever | حُمّى تكسير العظام (*break-bone fever*) | colloquial name; English kept in parentheses |
| *Aedes aegypti* | بعوضة الزاعجة المصرية (*Aedes aegypti*) | Latin name kept in parentheses, italic |
| *Aedes albopictus* | الزاعجة المُرقّطة (*Aedes albopictus*) | ⚠️ confirm preferred Arabic common name with reviewer |
| Vector / vector control | الناقل / مكافحة النواقل | |
| DENV (dengue virus) | فيروس الضنك (DENV) | acronym kept in Latin |
| Serotype (DENV-1…4) | النمط المصلي (DENV‑1…4) | Keep DENV labels in Latin |
| Extrinsic incubation period (EIP) | فترة الحضانة خارج الجسم (EIP) | ⚠️ confirm preferred MoH rendering |
| Midgut / salivary glands | المِعى المتوسّط / الغدد اللعابية | |
| Viremic | فيروسيّ الدم (viremic) | |
| Asymptomatic / pre-symptomatic | عديم الأعراض / ما قبل ظهور الأعراض | |
| Maternal (mother-to-child) transmission | الانتقال من الأمّ إلى الجنين | |
| Pre-term birth / low birthweight / fetal distress | ولادة مبكِّرة / انخفاض الوزن عند الولادة / ضائقة جنينية | |
| Blood products / organ donation / transfusion | منتجات الدم / التبرّع بالأعضاء / نقل الدم | |
| Mosquito breeding sites | أماكن تكاثر البعوض | |
| Standing water | المياه الراكدة | |
| Larvae / larvicide | اليرقات / مبيدات اليرقات | |
| Insecticide | المبيدات الحشرية | |
| Insecticide-treated net | الناموسية المعالَجة بالمبيدات | |
| Repellent (DEET, picaridin/icaridin, IR3535) | طارد الحشرات (DEET، البيكاريدين/الإيكاريدين، IR3535) | **product names kept in Latin** |
| Coils and vaporizers | اللفائف الطاردة (الحلزونية) والمبخِّرات | |
| Environmental management and modification | إدارة البيئة وتعديلها | |
| Community engagement / mobilization | مشاركة المجتمع وتعبئته | |
| Incubation period (4–10 days) | فترة الحضانة (4–10 أيام) | figure preserved |
| Warning signs | العلامات التحذيرية | |
| Paracetamol (acetaminophen) | الباراسيتامول (الأسيتامينوفين) | **medication — preserve** |
| NSAIDs (ibuprofen, aspirin) | مضادات الالتهاب غير الستيرويدية (الإيبوبروفين، الأسبرين) | **safety-critical: avoid** |
| Hospital care / hospitalization | الرعاية في المستشفى | |
| Space spraying | الرشّ الجوّي (الرذاذي) للمبيدات | |
| Vector surveillance | ترصُّد النواقل ومراقبتها | |
| Outbreak | الفاشية / التفشّي | |
| Global Arbovirus Initiative | المبادرة العالمية لمكافحة الفيروسات المنقولة بالمفصليات (Global Arbovirus Initiative) | initiative name kept in Latin too |
| 40 °C / 104 °F ; 25–28 °C | 40 °م / 104 °ف ؛ 25–28 °م | **both scales preserved** |
| 100–400 million infections; ~half the world's population | 100–400 مليون إصابة؛ نحو نصف سكان العالم | **figures preserved** |

---

## 6. Agent self-check flags (UNCERTAIN — must be resolved before sign-off)

Per project policy, unresolved flags **block** sign-off. Each must be marked `resolved` (with the
reviewer's adjudication) or `accepted-as-is` (with justification).

- `UNCERTAIN:source` — Drafted and revised **without a live fetch** of the WHO page (fetch attempted
  2026-07-24, not permitted by the environment). The English source-equivalent (§4) and all factual
  claims must be **reconciled line-by-line against the live WHO fact sheet**; record the page's
  publication/last-update date and retrieval date.
- `UNCERTAIN:license` — WHO reuse terms for this **specific page** are **asserted, not verified**
  (CC BY-NC-SA 3.0 IGO assumed); the allow-list entry `who-publications` is still
  `reviewStatus: provisional` with `sha256: null`. Confirm in writing, snapshot/hash the license
  text, and promote the entry **before delivery**. Do not ship if terms forbid translation.
- `UNCERTAIN:disclaimer-wording` — The WHO English disclaimer in §2 is the standard CC BY-NC-SA
  3.0 IGO wording; confirm it is the **exact** wording required for this source. The Arabic
  rendering of the disclaimer needs reviewer confirmation.
- `UNCERTAIN:safety` — The medication guidance (paracetamol; **avoid NSAIDs/aspirin/ibuprofen**)
  and the **warning-signs / "seek care immediately"** messaging are **safety-critical**. Verify
  wording precisely, including that no negation is inverted; **second independent reviewer
  required**.
- `UNCERTAIN:numbers` — Figures now included and must each be checked against the live source:
  ~**half the world's population** at risk; **100–400 million** infections/year; incubation
  **4–10 days**; symptoms **2–7 days**; recovery **1–2 weeks**; fever **40 °C / 104 °F**; EIP
  **8–12 days** at **25–28 °C**; viremic window **2 days before → 2 days after** fever; warning
  signs typically **days 3–7**. If any figure has been revised on the live page, update it there
  and in §4 and §5.
- `UNCERTAIN:terminology` — Confirm preferred Arabic common name for *Aedes albopictus*; that
  *الزاعجة المصرية* is the partner/MoH-preferred term for *Aedes aegypti*; and the preferred Arabic
  renderings of *extrinsic incubation period*, *viremic*, and *midgut*.
- `UNCERTAIN:vaccine` — Vaccine recommendations change; kept deliberately general (no product or
  brand names). Verify against current WHO/national guidance at delivery time.
- `UNCERTAIN:register` — Modern Standard Arabic is used throughout, with diacritics only where they
  disambiguate. Confirm the register and any dialect adaptation needed for the deploying community
  (e.g. Levantine/Maghrebi/Gulf audiences) with the partner.

---

## 7. Reviewer handoff & sign-off (PENDING)

**Reviewer qualification required:** qualified Arabic-speaking reviewer with health-translation
competence; **independent of the drafter** (the person who ran the drafting agent may not be the
sole sign-off reviewer). For this safety-critical document, a **second independent reviewer** is
required.

**Checklist (reviewer to complete in PR):**
- [ ] Accuracy: Arabic faithfully conveys the (reconciled) WHO source; no added/dropped meaning.
- [ ] Completeness: every section of the live fact sheet is represented (key facts, overview,
      transmission incl. mosquito→human / human→mosquito / maternal / other, symptoms, severe-dengue
      warning signs, diagnosis & treatment, vaccines, prevention & control, WHO response).
- [ ] Medical terminology preserved and consistent with §5 glossary and MoH/partner usage.
- [ ] Safety-critical content correct: warning signs, "seek care immediately," paracetamol vs.
      avoid-NSAIDs — no negation/instruction errors.
- [ ] Numbers/units match the live source exactly (see `UNCERTAIN:numbers` in §6).
- [ ] Cultural appropriateness, register, and readability for community health workers.
- [ ] All §6 `UNCERTAIN:` flags resolved or explicitly accepted-as-is.
- [ ] **License verified** (terms permit translation/derivatives), snapshot/hash + archive URL
      recorded, and the `who-publications` allow-list entry promoted to `reviewStatus: confirmed`.
- [ ] Attribution + **verbatim WHO translation disclaimer** present (EN + AR) and correct.
- [ ] Output license recorded as source-compatible (**CC BY-NC-SA 3.0 IGO**, not CC-BY).
- [ ] Provenance complete (source URL, version/date, retrieval date, license snapshot).

| Role | Name | COI declaration | Decision | Date |
|---|---|---|---|---|
| Drafter (agent) | Claude agent | n/a (not a sign-off) | Draft only | 2026-06-28 (rev. 2026-07-24) |
| Reviewer 1 (qualified, independent) | _________ | _________ | ☐ approve ☐ changes | ______ |
| Reviewer 2 (safety-critical, required) | _________ | _________ | ☐ approve ☐ changes | ______ |
| License/compliance reviewer | _________ | _________ | ☐ verified | ______ |

> **Definition of cleared:** all acceptance criteria met **and** qualified-reviewer sign-off
> recorded **and** license/attribution/disclaimer verified **and** provenance complete. Until then,
> this document is a **delivered draft**, not field-ready material.

---

## 8. Acceptance-criteria status / حالة معايير القبول

| # | Acceptance criterion | Status | Evidence / what remains |
|---|---|---|---|
| 1 | Full source guidance translated accurately | **Draft complete** — all fact-sheet sections rendered in Arabic (§3), incl. overview, full transmission section, figures, hospitalization, and WHO response | Line-by-line reconciliation against the **live** page is human-held (§6 `UNCERTAIN:source`) |
| 2 | Medical terminology preserved | **Met (draft)** — 30-entry EN↔AR glossary (§5); Latin taxonomic names, DENV serotype labels, drug and repellent names, and both temperature scales preserved | Reviewer to confirm MoH-preferred renderings (§6 `UNCERTAIN:terminology`) |
| 3 | Reviewed by a qualified Arabic-speaking reviewer (risk tier: medium) | **NOT MET — open, human-held** | Reviewer handoff, qualification bar, and checklist prepared (§7); second independent reviewer required (safety-critical content). The agent cannot self-certify this. |
| 4 | Source licence verified to permit translation + attribution/disclaimer recorded (not relicensed as CC-BY) | **Partially met** — automatable steps 1–5 verified (§1.1); attribution + verbatim WHO disclaimer recorded EN+AR (§2); output license recorded as CC BY-NC-SA 3.0 IGO, **not** CC-BY | Steps 6–9 (live fetch, snapshot + sha256 + archive URL, per-page terms confirmation, allow-list promotion to `confirmed`) remain open and **blocking** |

### Revision log

| Date | Change |
|---|---|
| 2026-06-28 | Initial draft: provenance, attribution/disclaimer, Arabic translation, English source-equivalent, glossary, flags, reviewer handoff. |
| 2026-07-24 | Coverage repair against the source fact sheet: added **Overview**, global-burden key facts (~half the world's population; 100–400 million infections/year; urban/semi-urban), full **Transmission** section (mosquito→human incl. midgut/salivary glands and EIP 8–12 days at 25–28 °C; human→mosquito viremic window; maternal transmission; blood/organ/transfusion routes), fever **40 °C/104 °F**, second-infection risk, home management with pain medicine, **hospitalization** for severe dengue, environmental management / community mobilization / active surveillance, and the **WHO response** section. §4 English source-equivalent and §5 glossary updated to match; added §1.1 license verification split (automatable-verified vs. held-human), §8 acceptance-criteria status, and `UNCERTAIN:register`. Live source fetch attempted and **not permitted** — source/license gates remain open. |

*End of document — delivered draft, pending qualified review.*
