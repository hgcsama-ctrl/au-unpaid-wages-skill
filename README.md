# au-unpaid-wages

A Claude skill that turns "my boss never paid me" into a tidy case file, a calm escalation
path, and a correctly lodged Fair Work Ombudsman enquiry. Built from a real case in Victoria,
Australia, with every personal detail removed.

一个帮助在澳洲追讨欠薪的 Claude skill：建立案件档案、按顺序催款（催款信 → 最后通知 → Fair Work
Ombudsman 在线申诉）、用聊天记录时间戳还原工时、把法律判断交给 FWO / JobWatch / 社区法律中心。
来自一个真实的维州案件，所有个人信息已剥离。

## What it does

- Sets up a case folder: timeline, evidence index, hours table, calculations, drafts.
- Enforces eight ground rules that keep the paper trail clean (nothing sent without the user's
  explicit approval, one final notice then silence, contact only the employer and regulators,
  no secrets in files, log everything).
- Provides templates for the chaser, letter of demand and final notice.
- Walks through the FWO "My account" online enquiry field by field, with the character limits
  and the form quirks observed on the live site.
- Explains employee-vs-contractor (sham contracting) evidence without deciding it, and points to
  free advice: FWO 13 13 94, JobWatch 03 9662 1933 (VIC), community legal centres, TIS 131 450.

## Install

Copy the `au-unpaid-wages/` folder into your skills directory:

- Claude Code: `~/.claude/skills/au-unpaid-wages/` (or `.claude/skills/` inside a project)
- Claude.ai / desktop: upload the folder or a `.skill` package via Settings → Skills

Then just describe the situation ("I haven't been paid for my shifts", "老板不给工资") and the
skill triggers.

## Layout

```
au-unpaid-wages/
├── SKILL.md                       workflow, ground rules, phases
├── references/
│   ├── fwo-my-account-walkthrough.md
│   ├── employee-vs-contractor-evidence.md
│   └── escalation-ladder.md
├── assets/templates/              case file skeleton, letters, FWO field sheet, handover
├── scripts/
│   ├── new_case.sh                scaffold a case folder
│   └── check_lengths.py           check drafts against FWO field limits
└── evals/evals.json               example prompts
```

## Not legal advice

This skill is a filing and drafting assistant. It does not give legal advice and it is not a
substitute for the Fair Work Ombudsman, a community legal centre, JobWatch or a lawyer. Laws,
rates, forms and phone numbers change: verify on the official sites before relying on them.

## Contributing

Issues and pull requests welcome, especially: form changes on the FWO site, state-specific
agencies outside Victoria, templates for other languages, and corrections from people who
practise employment law. Please never include real names, ABNs, addresses or screenshots.

## License

MIT
