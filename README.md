# 🧾 Recover

**Recover** is a program that scans a raw memory card file (e.g., `.raw`) and **recovers deleted JPEG images** by detecting JPEG file signatures and extracting the image data.

## 🧠 How It Works

- Reads the raw memory card data in 512-byte blocks
- Detects the start of a JPEG file based on signature:  
0xff 0xd8 0xff 0xe0 - 0xef  
- When a new JPEG is found:
- Closes the previous file (if any)
- Starts writing to a new JPEG file (e.g., `000.jpg`, `001.jpg`, etc.)
- Continues until all JPEGs are recovered

---

## 📂 Example Usage

```bash
$ make recover
$ ./recover memorycard.raw
```
Recovered images:  
<img src="https://github.com/user-attachments/assets/65252265-bc84-4ae9-90cf-2f7388331720" alt="Screenshot 1" width="300"/>
<img src="https://github.com/user-attachments/assets/a82df0f4-37cc-4f24-89b6-83f04f9d01d9" alt="Screenshot 2" width="300"/><br>
<img src="https://github.com/user-attachments/assets/9ee869eb-bf72-4da4-a057-9a2ef0a21534" alt="Screenshot 3" width="300"/>
<img src="https://github.com/user-attachments/assets/99107aeb-ed50-4ad3-ba9a-7a693712f99c" alt="Screenshot 4" width="300"/>

