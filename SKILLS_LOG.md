Template
## 2026-10-12: Task #, description
- **What I did:** (one or two sentences)
- **Tools used:** (dcmdump, pydicom, etc.)
- **What went wrong and how I fixed it:** (to help remember during interviews)
- **What I can explain:** (concepts I can answer questions on)
- **What I still don't understand:** (known knowledge gaps)

## 2026-10-12: Task 0, setup repo, install dependencies
- **What I did:** Initiated repository, wrote README.md, Updated pip and apt, Created and activated a Python virtualenv in WSL, installed dcmtk/python3 venv, created venv folder at ~/venvs/dicom 
- **Tools used:** markdown, linux cli, sudo, pip, apt, python3 3.10.12

## 2026-10-18: Task 1, DCMDUMP
- **What I did:** located pidicom test data files, printed sample data with dcmdump
- **Tools used:** dcmdump, dcmdump ... | less
- **What went wrong and how I fixed it:**     When I used the less tool without knowing how to navigate it I thought I broke my terminal. I opened a new one and immediately pressed h and found the navigation instructions in the help section.
- **What I can explain:** 
    How to navigate less (the tool that views dcmdump)
    Key | What it does
    | --- | --- |
    Space | Down one page
    b | Up one page
    ↓ / ↑ or j / k |  Down or up one line
    d / u | Down or up half a page
    g | Jump to the top
    G | Jump to the bottom
    /word + Enter | Search forward for word
    ?word + Enter | Search backward for word
    n | Next match
    N | Previous match (opposite direction)
    q | Quit
    h | Help screen listing every command
    -i + Enter | ignores case sensitivity
    
    Each line in dcmdump has certain elements, example: (0008,0060) CS [XX]        # 2, 1 Modality
    Element | Explanation
    | --- | --- |
    ```(0008, 0060)``` | is the tag (group, element)
    ```(CS)``` | The next two characters are the value type (VR). 
    | | CS is a short code string,
    | | UI is a UID, 
    | | PN is a person's name,
    | | US is an unsigned number.
    ```[XX]``` | The value itself
    ```# 2, 1``` | length in bytes, how many values
    ```Modality``` | The tag's readable name - this is the value you search for

    using less and grep to search for values. example: SOPInstanceUID returns:
    ```py
    (0002,0003) UI [1.3.6.1.4.1.5962.1.1.1.1.1.20040119072730.12322] #  48, 1 MediaStorageSOPInstanceUID
    (0008,0018) UI [1.3.6.1.4.1.5962.1.1.1.1.1.20040119072730.12322] #  48, 1 SOPInstanceUID
    ```

- **What I still don't understand:** What each element in the return strings represents. I understand the longer UID is the location of the object but not how it works.