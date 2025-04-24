# TESTAR GitHub Action

This GitHub Action runs the [TESTAR scriptless tool](https://github.com/TESTARtool/TESTAR_dev) for testing Web applications.

## ✅ Features

- Test Web (Selenium) SUTs
- Automatically downloads and runs the latest TESTAR release
- CI-friendly configuration using GitHub Actions

## 🔧 Inputs

| Input | Description | Default |
|-------|-------------|---------|
| `version` | TESTAR version to download (e.g. `v2.6.37`) | `v2.6.37` |
| `application_name` | Name of the SUT being tested by TESTAR (for report identification) | **Required** |
| `sut` | Web URL of the SUT to be tested by TESTAR | **Required** |
| `sequences` | Number of test sequences | `5` |
| `sequence_length` | Length of each sequence | `10` |
| `suspicious_titles` | Regex for suspicious titles | `.[eE]rror.\|.[eE]xcep[ct]ion.` |

## 📦 Example Usage (Web SUT)

- Required `sut` parameter

```yaml
- uses: ferpasri/testar-action@v1
  with:
    sut: 'https://para.testar.org/parabank'
```

- Other parameters

```yaml
- uses: ferpasri/testar-action@v1
  with:
    application_name: 'parabank'
    sut: 'https://para.testar.org/parabank'
    sequences: '3'
    sequence_length: '5'
    suspicious_titles: '.[eE]rror.|.[eE]xcep[ct]ion.|.[iI]nvalid.'
```