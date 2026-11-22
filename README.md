# File validation tests

All fixtures contain synthetic test bytes only. They contain no personal information, credentials, or business records.

| File | Targeted requirement | Download |
|---|---|---|
| 01-invalid-naupa.txt | NAUPA II conformity | [Download](https://raw.githubusercontent.com/CEOFOUNDER/test/main/01-invalid-naupa.txt) |
| 02-disallowed-extension.csv | Allowed file extension | [Download](https://raw.githubusercontent.com/CEOFOUNDER/test/main/02-disallowed-extension.csv) |
| 03-overlong-record.rpt | Maximum record length | [Download](https://raw.githubusercontent.com/CEOFOUNDER/test/main/03-overlong-record.rpt) |
| 04-wrong-first-character.hrs | First character must be 1 | [Download](https://raw.githubusercontent.com/CEOFOUNDER/test/main/04-wrong-first-character.hrs) |
| 05-wrong-last-record.rpt | Last record must start with 9 | [Download](https://raw.githubusercontent.com/CEOFOUNDER/test/main/05-wrong-last-record.rpt) |
| 06-control-character.txt | No control characters | [Download](https://raw.githubusercontent.com/CEOFOUNDER/test/main/06-control-character.txt) |
| 07-high-level-character.hrs | No high-level characters | [Download](https://raw.githubusercontent.com/CEOFOUNDER/test/main/07-high-level-character.hrs) |
| 08-over-1GB.txt | Maximum file size: 1 GB | [Download](https://github.com/CEOFOUNDER/test/releases/download/v1.0/08-over-1GB.zip) |

The large fixture is distributed in a ZIP release asset. Extract `08-over-1GB.txt` before uploading it to the software under test; the extracted file is exactly 1,073,741,825 bytes. The archive has been verified against the original file using SHA-256.

The four-byte NAUPA fixture contains `1 CR LF 9`: it passes the listed basic file checks but fails NAUPA conformity. CR/LF is treated as the expressly permitted record separator. The other fixtures target additional upload checks and also fail NAUPA conformity; these are not valid reports with a single NAUPA field changed.

For each fixture, the issue statement is: "A file of type [extension] that breaks [targeted requirement] can be uploaded by the system." Use that statement only after confirming the actual upload succeeds. Upload acceptance for later validation does not establish successful compliance validation. No target application testing has been performed.
