# 🧪 LAB 07 (2 Hours) — Interactable 3: Lore Object + Popup Panel

Includes scripts

---

## Goal

Select a lore object to open a panel with Title + Body.

---

## A) Create Lore Panel Canvas

UI → Canvas → rename **LorePanel_Canvas**

Render Mode = World Space

Set Transform: Position: (0, 1.4, 1.0) | Rotation: (0, 180, 0) | Scale: (0.002, 0.002, 0.002)


Add TMP Title: **TXT_LoreTitle**

Add TMP Body: **TXT_LoreBody**

Disable the canvas (unchecked active box in Inspector)

---

## B) Create Lore Tablet Prefab

3D Object → Cube → rename **LoreTablet**

Add **XR Simple Interactable**

Drag into Prefabs folder

---

## C) Script: LoreObject.cs

Create script and paste:

```csharp
using TMPro;
using UnityEngine;

public class LoreObject : MonoBehaviour
{
    public string title = "Lore Title";
    [TextArea(3,8)]
    public string body = "Lore text here...";

    public GameObject loreCanvas;
    public TMP_Text titleText;
    public TMP_Text bodyText;

    public void ShowLore()
    {
        loreCanvas.SetActive(true);
        titleText.text = title;
        bodyText.text = body;
    }

    public void HideLore()
    {
        loreCanvas.SetActive(false);
    }
}
```
Attach to LoreTablet prefab.

---

## D) Wire References (VERY IMPORTANT)

Select **LoreTablet** in scene and assign:

- loreCanvas → drag **LorePanel_Canvas**  
- titleText → drag **TXT_LoreTitle**  
- bodyText → drag **TXT_LoreBody**

---

## E) Connect XR Event

In **LoreTablet prefab**:

Select **Select Entered** event → `+` → drag **LoreTablet** → **LoreObject.ShowLore()**

---

## F) Close Button

Add UI Button on **LorePanel_Canvas**

OnClick → drag **LoreTablet** → **LoreObject.HideLore()**

---

## Submission Task

Create **3 lore tablets** with different text and show open/close.

Filename: Lab07_<ITNo>.mp4


---

## Next Lab

Lab 08: Objectives + timer + feedback (connect everything).

---

