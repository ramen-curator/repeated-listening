# Activity 6.1: Repeated Listening Fluency Trainer

**English** | [简体中文](README_ZH.md) | [日本語](README_JA.md)

A zero-dependency, single-file browser application designed to build foreign-language listening decoding speed and automaticity. Grounded in **Activity 6.1: Repeated Listening** from Paul Nation's *What Do You Need to Know to Learn a Foreign Language?*, this trainer uses randomized audio prompts and progressive speed controls to help learners instantly recognize high-frequency words, numbers, and phrases without mental translation.

## Features

- **Multi-Language Interface (`zh-CN` / `en` / `ja`)**: Switch seamlessly between English, Simplified Chinese, and Japanese UI in the top-right header. Unmodified preset dataset titles and glosses automatically localize to match your active UI language.
- **Two Training Modes**:
  - **Pointing Mode (`point`)**: Replicates Paul Nation's classic physical pointing exercise—listen to the randomized audio stream and visually track or point to the matching card on the board before the next item is spoken.
  - **Quiz Mode (`quiz`)**: Click the matching card during the pause window for immediate correctness feedback and real-time score tracking.
- **Granular Speed & Pacing Controls**:
  - **Speech Rate**: Adjust TTS playback speed from `0.6x` to `1.6x` (step `0.05x`, default `1.0x`).
  - **Pause Interval**: Configure the reaction window between prompts from `0.2s` to `5.0s` (step `0.1s`, default `1.8s`).
  - **Repetition Count**: Set how many times each item repeats per session (`1` to `20` repetitions per item, default `4`), automatically generating a randomized sequence.
- **Custom Datasets & Built-In Presets**:
  - Includes 5 ready-to-use presets: **English Basic Numbers (1–10)**, **English Days of the Week**, **English Months**, **Japanese Basic Numbers (1–10)**, and **Spanish Common Foods**.
  - Create, edit, save, and delete your own custom datasets using a simple `spoken text | card display label` line format.
- **Board Aids & Playback Shortcuts**:
  - Toggle phonetic/spoken text subtitles on cards (`Show Subtitles`) to adjust difficulty.
  - Shuffle board card positions (`Shuffle Board`) to prevent spatial memorization.
  - Full playback controls: **Start**, **Pause / Resume** (`Space` hotkey), **Replay Current Word**, and **Stop**.
- **100% Local & Private**: Powered by your browser's native Web Speech API (`window.speechSynthesis`) and `localStorage` (`repeated_listening_datasets`, `repeated_listening_lang`). No server, no API keys, and no external dependencies required.

## Preview & Demo



https://github.com/user-attachments/assets/77227499-52e8-466d-81ee-0597282cb9fa

## Pedagogical Background

This tool implements **Activity 6.1: Repeated listening** within the **Fluency Development** strand of Paul Nation's *Four Strands* framework (*What Do You Need to Know to Learn a Foreign Language?*, [PDF](https://www.wgtn.ac.nz/lals/resources/paul-nations-resources/paul-nations-publications/publications/documents/foreign-language_1125.pdf)):

> **Activity 6.1: Repeated listening**
>
> Have someone record the numbers from one to ten in the foreign language in a random order, for example: 6, 3, 8, 1, 7, 10, 2, 9, 4, 5, 3, 10, 3, 6. Each number should occur several times in a different place so that you have plenty of opportunity to hear the same number over and over again without knowing when it is going to come. Write the numbers 1 to 10 in order on a piece of paper, and as you listen to the recording, point to the number that you hear. When you can do this quickly and easily, increase the speed and do it again. Keep doing this until you can easily recognize the spoken numbers. It is best to spread the practice over several days rather than doing it all in one session.
>
> This activity uses repetition and increasing speed to quickly develop fluency in understanding numbers. You can also use it to practice days of the week, months, greetings, food names, and many other items.

## Getting Started

1. Clone or download the [ramen-curator/repeated-listening](https://github.com/ramen-curator/repeated-listening) repository:
   ```bash
   git clone https://github.com/ramen-curator/repeated-listening.git
   ```
2. Open [`index.html`](https://github.com/ramen-curator/repeated-listening/blob/main/index.html) directly in any modern desktop or mobile browser (Chrome, Edge, Safari, or Firefox).
3. Select your preferred UI language (**中文** / **English** / **日本語**) in the top-right corner.

## How to Use

| Step | Action | Details |
| :--- | :--- | :--- |
| **1. Configure Dataset** | Select a preset or create a custom set | Choose from the 5 built-in presets or click **New** to define your own items using one `spoken word \| card label` pair per line, then click **Save**. |
| **2. Select TTS Voice** | Pick a target-language voice | Choose a system/browser TTS voice in **Voice Selection** that matches the language of your dataset (e.g., `en-US`, `ja-JP`, `es-ES`). |
| **3. Set Pacing & Mode** | Adjust speed, interval, and mode | Start with a comfortable **Speech Rate** (`1.0x`) and **Pause Interval** (`1.8s`). Choose **Pointing Mode** for self-paced finger/eye tracking or **Quiz Mode** for interactive clicking. |
| **4. Train & Accelerate** | Run sessions and increase speed | Click **Start** (use `Space` to pause/resume). Once recognition feels effortless, gradually raise the **Speech Rate** or shorten the **Pause Interval** across sessions. |

### Custom Dataset Format

Enter one item per line in the dataset editor using the pipe (`|`) separator:

```text
spoken_text | display_label
```

- **`spoken_text`**: The foreign-language word or phrase read aloud by the Web Speech API TTS engine (also shown as a card subtitle if enabled).
- **`display_label`**: The meaning, numeral, or prompt displayed prominently on the recognition board card.
- If no `|` is provided on a line, the same text is used for both speech synthesis and the card label.

**Example (Japanese Days of the Week):**

```text
げつようび | Mon (月)
かようび | Tue (火)
すいようび | Wed (水)
もくようび | Thu (木)
きんようび | Fri (金)
どようび | Sat (土)
にちようび | Sun (日)
```

## Origin & Credits

- Initial prototype generated with Gemini 4 Argon on October 14, 2026 ([original AI Studio prompt conversation](https://www.google.com/search?q=https://aistudio.google.com/prompts/1t3MhKqE3BqjXn_Hh8lqB5R6oU-dE8vN_)), subsequently expanded with trilingual UI localization (`zh-CN` / `en` / `ja`) and automatic preset translation.
- Pedagogical methodology by **Paul Nation**.

## License

Released under the [MIT License](https://github.com/ramen-curator/repeated-listening/blob/main/LICENSE).