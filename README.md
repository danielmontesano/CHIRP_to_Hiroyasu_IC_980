This is a fork of the original work by **[lu7cgj](https://github.com/lu7cgj/CHIRP---Hiroyasu-IC-980-PRO-KSUN-5200D)**.
Also see the fork of **[rulerofoz](https://github.com/rulerofoz/CHIRP---Hiroyasu-IC-980-PRO-KSUN-5200D-ABBREE-AR-8118)**, which addresses some of these problems. 

Please, see both githubs for detailed instructions. 

I have only tested this with UV-5R in Chirp and Hiroyasu IC 980 with SF-8118, downladed from **[HamRadioLife](http://hamradiolife.org/cpssoftware/Hiroyasu_IC-980Pro.zip)**

## What's fixed in this fork
- Corrected python paths in linux.

- Removed the 240 broken bases/baseN.ysf templates (wrong padding, caused first 16 channels to be misread) in favor of one real empty template + a dynamically computed active-channel bitmap. I created a new base (empty.ysf, an empty channel list created with SF-8118 sowftare) and used for reference for all the posible configurations.
  
- Fixed CTCSS tone matching: normalized values like "100"/"67" to one decimal before lookup (previously an tone without decimals silently failed and wrote OFF).
  
- Fixed DCS code matching: zero-pad codes like "23" → "023" before lookup, and fail safely to OFF instead of writing a wrong raw value when a code isn't found.
  

Disclaimer: I have used Claude and ChatGPT to help me perform the modifications in the scripts. 
