# Sinhala-Addendum-Phonetic-Rime
Rime port of the Sinhala-Addendum-Phonetic transliteration scheme based input method.
# Setup Instruction
## 1. Basic Installation
- Download the schema and dictionary files
- Install the rime frontend for your platform
- Put the schema and dictionary files to user folder, and select the schema (follow the platform rime frontend's instructions
- [Optional] Add `style/preedit_type: preview` in your frontend's configuration (weasel.yaml for windows etc)
## 2. Weasel/Windows Specific Instruction
As Rime is targetted at chinese speakers, rime will register itself as a chinese IME in the language, while this is mostly inconsequential, this can cause
compatibility issues with some apps like Notepad or OpenOffice.  
    
In the future I plan to create an installer that automatically handles this, but for the time being you'll have to either run the `scripts/weasel-sinhala.reg` file or manually edit the registry for this.
- Open RegEdit and navigate to `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\CTF\TIP\{A3F4CDED-B1E9-41EE-9CA6-7B4D0DE6CB0A}\LanguageProfile`
- Find the entry there which is enabled, which by default should be the entry under the simplified chinese language code (804) (`0x00000404\{3D02CAB6-2B8E-4781-BA20-1C9267529467}`)
![image](https://github.com/user-attachments/assets/9fbb7384-840f-497c-9707-1c4233d7a9c5)
- Rename the containing reg directory to instead have the sinhalase language code (456), so `0x00000804` -> `0x0000045b` (you can change any weasel entry there, just make sure to enable the one you change and disable the others)
  - Please install the Sinhala language pack before doing this, lest you suffer the tormentations of windows

# Usage Guide
Please refer to the [usage guide of the m17n port](https://github.com/AdelinaM17n/Sinhala-Addendum-Phonetic-M17n/blob/main/usage_guide.markdown) for the time being, it should be mostly accurate.

# Credits 
- Huge thanks to [Lotem](https://github.com/lotem) from the rime team for [helping me figure out]([https://github.com/lotem](https://github.com/rime/home/discussions/1729)) how to adapt Rime for this.   
- The Weasel language workaround ([reference issue](https://github.com/rime/weasel/issues/438)) was figured out by [Reniastyc de El Magnifico ](https://github.com/Reniastyc), and brought on to my attention by [SimplyKyle](https://github.com/JustSimplyKyle)
