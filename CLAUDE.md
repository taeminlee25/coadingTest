# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 언어

- 모든 응답과 코드 주석은 **한국어**로 작성한다. 코드 식별자와 알고리즘 이름은 영어 그대로 둔다.

## 학습 방식

- 이 저장소는 코딩테스트 공부용이다. 사용자가 요청하기 전에는 `solution` 본문을 대신 채우지 않는다.
- 문제 풀이를 도울 때는 `cote-tutor` 스킬을 따른다.

## What this repo is

Personal solutions to algorithm exercises from a lecture course (알고리즘 문제풀이), written in plain JavaScript. There is no build step, no test framework, and no npm scripts. The only dependency is Prettier.

## Structure and conventions

- Each problem is one standalone HTML file. The file name is the problem title in Korean, and the file sits in a folder named after the topic/chapter (e.g. `기본문제풀이/`, `문자열 탐색/`, `2차원 탐색/`, `완전탐색/`, `효율성/`, `자료구조/`, `정렬과그리디/`, `재귀함수/`).
- Every file follows the same template: `<meta charset="UTF-8">`, `<title>출력결과</title>`, and one inline `<script>` that defines `function solution(...)` (plus any helper functions), builds the sample input by hand, and calls `console.log(solution(...))`.
- To add a new problem, copy that template into the right topic folder (create the folder if it's a new chapter). Keep the comments in Korean, like the existing files.
- Some files are unfinished stubs with an empty `solution` body (e.g. `재귀함수/재귀함수.html`). Those are the user's own exercises in progress.

## Running a solution

Open the HTML file in a browser and read the output in the DevTools console. To run it headlessly with Node from Git Bash, pull out the script body:

    sed -n '/<script>/,/<\/script>/p' "정렬과그리디/마굿간.html" | sed '1d;$d' | node

This only works for files that use `console.log` and no DOM APIs.

## Formatting

    npx prettier --write "<path/to/file.html>"

`.prettierrc`: `tabWidth: 4`, `semi: true`, `trailingComma: "all"`. Many existing files predate this config (some are missing semicolons, for example). Format only the files you touch, not the whole repo.
