# 🎧 Audio Timestamp Labeling Tool

This Streamlit app allows research assistants to label when a participant starts and stops speaking in recorded audio clips, or to discard unusable ones.

---

## 📁 Setup Instructions

### 1. **Download the Data**

* Download all folders from the following Google Drive link:
https://drive.google.com/drive/folders/175XzKYtJUalgK1Yw23dN1Y2rlX33MBPN?usp=share_link
Note: You will need to request access using a Stanford-affiliated Google account.
* Place the folders in the **same directory** as this `README.md` file and the `audio_labelling.py` script.
* Your folder structure should look like this:

```
/Labelling/
├── README.md
├── audio_labelling.py
├── haGCTJT6sYUoVBtuftbldUpKtE82_efschl-hwsch-39691ace/
└── quaGipSF2vZx7HFKMMQP2Zr3aH62_efschl-hwsch-14e02ac2/
```

### 2. **Install Requirements**

Create a virtual environment (optional but recommended), then install the required Python packages:

```bash
pip install -r requirements.txt
```

### 3. **Launch the Streamlit App**

From the same directory, run:

```bash
streamlit run audio_labelling.py
```

### 4. **Choose Your Task Type (Letters or Numbers)**

In the file `audio_labelling.py`, go to **line 8** and set the type of task you want to label:

```python
audio_file_type = "Numbers"  # or change to "Letters"
```

* Set it to `"Numbers"` to label number-based RAN tasks.
* Set it to `"Letters"` to label letter-based RAN tasks.

This way, you can divide the work across multiple people—each working on a different type.

---

## 🧐 How to Use the App

* You'll be presented with one audio file at a time.
* Listen to the full clip using the audio player.
* If the participant **spoke clearly**:

  * Enter the **start time** and **end time** in seconds.
  * Click ✅ **Save and Next** to save and move on.
* If the clip is **inaudible, empty, or unclear**, click 🗑️ **Discard and Next** instead.

---

## ✅ Output

* Your labels are saved automatically to a CSV file named:

```
audio_timestamps_{task}.csv
```

This file stores the start and end times (or \[0, 0] if discarded) for each processed audio clip.

---

Send these CSV's back when complete!
