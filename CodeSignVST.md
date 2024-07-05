# Codesigning a VST

    Once a vst is compiled it needs to be codesigned in order to run in Ableton. Follow the below to codesign your VST.

 - Find your developer ID:
    ```bash
    security find-identity -v -p codesigning
    ```
- Sign the vst
    ```bash
    codesign --sign <developer_id> --timestamp <path_to_vst>
    ```
- If the above fails for finder information run
    ```bash
    xattr -c <path_to_vst>
    ```
    to strip off finder information and re-run the codesign command