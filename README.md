# humanizer-ru

🇷🇺 [Русская версия](README.ru.md)

A Claude skill that removes signs of AI generation from Russian-language blog content.

## What it does

- Cleans lexical AI markers: mentor tone, emotional inflation, bureaucratic register, grandiose openers and endings
- Fixes structural patterns: symmetrical paragraphs, list mania, lists of exactly three
- Guards against the opposite problem — doesn't let the text drift into TikTok copy or LinkedIn-blogger style

## Target genres

✅ Telegram channel posts  
✅ Articles on vc.ru, Habr  
✅ Analytical breakdowns, essays, tutorials  

## Installation

Download `humanizer-ru.skill` from [Releases](../../releases) and import it into Claude.

## Usage

The skill triggers automatically when you say (in Russian):
- «перепиши более живо» — rewrite it more lively
- «сделай менее ИИ-шно» — make it less AI-ish
- «звучит как ChatGPT» — sounds like ChatGPT
- «слишком сухо / шаблонно» — too dry / formulaic

It also applies proactively after any Russian blog text longer than a paragraph is generated.

## Version

v1.0.0
