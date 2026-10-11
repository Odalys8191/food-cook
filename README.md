# Food Cook · Cooking insights as reusable skills

[简体中文](README.zh-CN.md) | English

A collection of Codex cooking skills built from independently organized book insights and household applications. The repository can grow as more cooking books are studied; each skill records its sources and turns useful principles into cooking decisions.

The first skill, `food-lab-cook`, turns ingredients you already have into a practical home-cooking plan. It asks about flavor and texture first, then recommends quantities, heat, timing, and observable signs of doneness. It draws on principles discussed in J. Kenji López-Alt’s *The Food Lab* and uses its own interaction flow and household applications.

This is an independent project, not an official companion or endorsed by the author or publisher. Skill instructions and reference notes are currently written in Chinese; this README provides English installation and usage guidance.

## Available skills

| Skill | Main reference | Purpose |
| --- | --- | --- |
| [food-lab-cook](skills/food-lab-cook/SKILL.md) | *The Food Lab*, J. Kenji López-Alt | Ingredients → flavor and texture preferences → practical cooking steps |

## Quick start

Download the repository and keep the complete `skills/food-lab-cook` folder, including `references/` and `agents/`.

For a fresh user-level installation, run these commands from the downloaded repository root:

```sh
mkdir -p ~/.agents/skills
cp -R skills/food-lab-cook ~/.agents/skills/
```

If `food-lab-cook` is already installed, update that copy after reviewing it. Avoid installing duplicate copies under the same skill name. Current [OpenAI documentation](https://learn.chatgpt.com/docs/build-skills) lists `~/.agents/skills` for user-level discovery and `.agents/skills` for repository-level discovery. Follow your host’s configured location; if the skill does not appear, restart Codex.

Invoke it explicitly:

```text
Use $food-lab-cook. I have chicken thighs and mushrooms.
Ask about my flavor preferences first. Please respond in English.
```

An illustrative conversation:

> **You:** I have chicken thighs and mushrooms.  
> **Assistant:** Would you like garlic and soy, mildly spicy, or light and savory? Do you prefer tender or browned?  
> **You:** Garlic and soy, nicely browned. Two people, a frying pan, 30 minutes.  
> **Assistant:** Recommends one suitable dish, states preparation assumptions, and provides quantities, numbered steps, heat and timing ranges, chicken’s safe internal temperature, and one or two explanations of the method.

If you already state your preferences, the skill uses them. You can also say “choose for me.”

## What food-lab-cook does

- Adapts the flavor question to the ingredients instead of offering a fixed menu.
- Chooses a method around browning, tenderness, moisture, texture, available cookware, and time.
- Gives measurements in grams, milliliters, and Celsius, with stopping cues alongside timing.
- Suggests substitutions and responds to feedback such as “too salty” or “not crisp.”

No book file, custom scripts, or additional API credentials are required. You need a Codex environment that supports local skills. Confirmed preferences are reused within the conversation; the skill does not automatically save them globally.

## Files

```text
README.md
README.zh-CN.md
.gitignore
skills/food-lab-cook/
├── SKILL.md
├── agents/openai.yaml
└── references/
    ├── core-insights.md
    ├── ingredient-playbook.md
    ├── taste-and-sauces.md
    └── food-safety.md
```

The [skill entry point](skills/food-lab-cook/SKILL.md) loads the relevant reference notes as needed. These notes cover cooking decisions, ingredients, sauces, and household food safety. Book page references are edition-specific research locators, not instructions to obtain a particular PDF.

## Sources and validation

Primary inspiration: J. Kenji López-Alt, *The Food Lab: Better Home Cooking Through Science*, W. W. Norton, 2015; Chinese edition: 《料理实验室：科学创造美味》. See the [author’s book page](https://www.kenjilopezalt.com/books).

Food-safety guidance is separately sourced from [FoodSafety.gov](https://www.foodsafety.gov/food-safety-charts/safe-minimum-internal-temperatures) and the [Hong Kong Centre for Food Safety](https://www.cfs.gov.hk/sc_chi/multimedia/multimedia_pub/multimedia_pub_fsf_139_04.html), checked on 2026-10-11. It serves a different purpose from texture-oriented cooking temperatures in the book.

The `food-lab-cook` format has been validated. Three simulated response scenarios checked preference-first behavior, explicit constraints, and ingredient-specific handling. These were response checks, not physical cooking trials; generated recipes still require judgment about actual ingredients and equipment.

## Adding insights from more books

- Record the author, title, edition, and topic or page locator for each source. Keep source-derived principles distinct from this project's household adaptations.
- Add a separate folder under `skills/` when a new book supports a distinct workflow. Extend an existing skill when the new material improves the same workflow, keeping attribution near the relevant rule.
- Write concise decision guidance in new wording. Do not reproduce a book's chapter structure, narrative explanations, illustrations, or a comprehensive recipe collection.
- Where sources disagree, state the ingredient, technique, or equipment conditions that explain the difference rather than inventing a universal rule.
- Review each addition's publication rights and verify representative ingredient-and-preference scenarios. The current review does not clear future books or additions automatically.

## Copyright and publication boundary

**The current, text-only skill is a reasonable candidate for public GitHub publication with the boundaries below. This is a qualified assessment, not rights-holder permission or a guarantee against claims.**

Copyright distinguishes underlying ideas and methods from their expression. Cooking principles can be applied, while original explanatory prose, photographs, illustrations, and creative selection or arrangement may be protected. See [WIPO’s explanation](https://www.wipo.int/en/web/copyright/protection) and the [U.S. Copyright Office’s Circular 33](https://www.copyright.gov/circs/circ33.pdf).

The reviewed skill contains reworded principles and separately organized household applications; no book scans, illustrations, long quotations, or complete original-book recipes were identified. This review covered the skill files and publication boundaries; it did not compare the wording line by line with the original book. Rewording and attribution alone do not establish non-infringement. Under [China’s Copyright Law, Articles 13–16 and 24](https://zscqj.beijing.gov.cn/zscqj/zwgk/flfg18/436481084/index.html), adaptations and compilations must respect the original work’s rights, and personal-study exceptions do not give blanket permission for public redistribution.

The assessment applies to the current `food-lab-cook` files only. Publish skill instructions, independently written references, and repository documentation. Exclude books, cover images, scans, full OCR text, and unauthorized download links. This project is a cooking aid, not a replacement for its source books.

Prepare releases from a clean directory containing only reviewed publication files. Keep private reading materials outside the publishable tree and do not import Git history containing them. `.gitignore` prevents ordinary future additions but does not remove existing Git objects or history.

## License status

No explicit open-source license has been selected. Publishing on GitHub permits viewing and forking under GitHub’s terms; it does not automatically grant unrestricted reuse of protected repository text. See [GitHub’s licensing guidance](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository).

This project claims no exclusive rights over cooking facts or methods. Any future license must cover only material the publisher has authority to license; it cannot grant rights to the book, its translation, or other third-party works.
