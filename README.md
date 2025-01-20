# DUALKEY - Seedphrase Encryption and Decryption Tool

This is a simple Python script for locally encrypting and decrypting seed phrases using a 4-digit encryption key and an offset value.

This allows you to reduce the risk of compromise when storing or sending your seed phrases digitally.

**MEMORIZE YOUR ENCRYPTION KEYS. Always clear your terminal after use.**


## How It Works

- **Encryption:** The ASCII value of each character is multiplied by the encryption key and subtracted by the offset.
- **Decryption:** The process is reversed to retrieve the original text.

## Requirements

- Python 3.7 or higher

## Usage Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/ilovespectra/dualkey.git
   cd dualkey
   ```

2. Run the script using:
   ```bash
   python3 dualkey.py
   ```

1. Follow the on-screen prompts:
   - Enter a **4-digit encryption key** (e.g., `1234`).
   - Enter an **offset value** (must be a 4 to 6-digit number, e.g., `123456`).
   - Choose `(E)` for encryption or `(D)` for decryption.
   - Enter text (up to **300 characters** for encryption).

Handling 24-Word Seed Phrases:

If your seed phrase contains 24 words, split it into two 12-word halves and encrypt them separately.

Example:
```sql
First half: "abandon ability able about above absent absorb abstract absurd abuse access accident"
Second half: "accuse achieve acid acoustic acquire across act action actor actress actual adapt"
```

## Example Usage

### Encrypting:
```
    DDDDD   U   U   AAAAA   L       K   K   EEEEE   Y   Y
    D    D  U   U  A     A  L       K  K    E        Y Y
    D    D  U   U  AAAAAAA  L       KKK     EEEE      Y
    D    D  U   U  A     A  L       K  K    E         Y
    DDDDD   UUUUU  A     A  LLLLL   K   K   EEEEE     Y

Seedphrase Encryption/Decryption Tool

Enter encryption key (4-digit number): 1234
Enter offset value (4 to 6 digit number): 123456
Do you want to (E)ncrypt or (D)ecrypt? E
Enter text to encrypt (max 300 characters): hello world
Encrypted Text: 4880 1178 9816 9816 13518 -83968 23390 13518 17220 9816 -56
```

### Decrypting:
```
    DDDDD   U   U   AAAAA   L       K   K   EEEEE   Y   Y
    D    D  U   U  A     A  L       K  K    E        Y Y
    D    D  U   U  AAAAAAA  L       KKK     EEEE      Y
    D    D  U   U  A     A  L       K  K    E         Y
    DDDDD   UUUUU  A     A  LLLLL   K   K   EEEEE     Y

Seedphrase Encryption/Decryption Tool

Enter encryption key (4-digit number): 1234
Enter offset value (4 to 6 digit number): 123456
Do you want to (E)ncrypt or (D)ecrypt? D
Enter the encrypted text to decrypt: 4880 1178 9816 9816 13518 -83968 23390 13518 17220 9816 -56
Decrypted Text: hello world
```

## Testing and Experimentation

- Try encrypting and then decrypting the same phrase with the same key and offset to verify functionality.
- Ensure to use a 4-digit encryption key and offset values within the required range.

## License

This project is open-source and available under the MIT License.
