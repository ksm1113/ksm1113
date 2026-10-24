### ksm1113

크립토 트레이딩 보조 도구를 Claude Code로 만들고 있습니다. 대부분 Node.js / Python이고, 조회·감시·기록 위주입니다. 자동 매매 코드는 아직 없습니다.

## 레포 한눈에 보기

| 레포 | 공개 | 하는 일 | 상태 | 스택 |
|---|---|---|---|---|
| [cowork-trading-stack](https://github.com/ksm1113/cowork-trading-stack) | Public (fork) | Claude Code · Codex로 바이브 코딩하는 법 입문 가이드(한국어). 원본 [coinmage777/cowork-trading-stack](https://github.com/coinmage777/cowork-trading-stack) | 참고용 fork | Python, TypeScript, Rust |
| newlisintbot | Private | 거래소 9곳(CEX 5, Perp DEX 4)의 신규 상장 공지를 감시하고, 거래 가능한 후보 페어를 찾음 | 감시·후보 검색까지. 매매 미구현 | Node.js |
| LP_Dashboard | Private | 내 LP 포지션을 온체인에서 직접 읽어 보여주는 로컬 대시보드. 읽기 전용 | 동작 중 | Node.js, Express, viem |
| telegram-obsidian-collector | Private | 텔레그램 채널 글을 모아 옵시디언 노트로 저장. 읽기 전용 | 매일 자동 실행 | Python, Telethon |
| vault-tools | Private | 옵시디언 볼트 점검(깨진 링크, 빠진 메타)과 프로젝트 지표 갱신 스크립트 2개 | 동작 중 | Python |
| lp-auto-bot-design | Private | LP 자동 운용 봇 설계 문서 | 설계만 있고 코드 없음 | 문서 |

## 서로 어떻게 이어지나

```
텔레그램 채널 ──> telegram-obsidian-collector ──> 옵시디언 볼트 <── vault-tools (점검·지표 갱신)
거래소 공지   ──> newlisintbot                     (후보 페어 파일로 전달)
온체인 데이터 ──> LP_Dashboard                     (화면으로 표시)
                  lp-auto-bot-design               (LP 자동 운용 설계 문서, 코드 없음)
```

- `telegram-obsidian-collector`는 `vault-tools`의 검사 코드를 불러 쓰기 때문에 두 레포를 같은 부모 폴더에 나란히 둡니다.
- 모든 도구는 로컬 PC에서 돌고, 키와 지갑 정보는 레포에 올리지 않습니다.

Private 레포는 이름과 한 줄 설명만 공개합니다.
