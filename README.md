# 3d-modeling

3D 建模專案 — 主要用 FreeCAD Python macro 方式建模，輸出 STL 進行 3D 列印。

## 工作流程

1. 在 `macros/` 撰寫或修改 `.FCMacro` 腳本
2. FreeCAD → Tools → Macros → Execute
3. 確認外觀後 File → Export → `.stl` 存入 `designs/`
4. 切片（Bambu Studio / Cura）→ 列印

## 目錄結構

```
3d-modeling/
  macros/       ← FreeCAD Python macro (.FCMacro)
  designs/      ← 輸出的 .FCStd 與 .stl 檔案
  reference/    ← 參考照片、尺寸量測記錄
  README.md
  .gitignore
```

## 現有設計

| 檔案 | 說明 | 狀態 |
|------|------|------|
| `macros/pcb_lego_box.FCMacro` | PCB 卡扣盒，背面樂高 Technic 孔（3×3），尺寸可調 | 待列印測試 |

## 設計參數說明（pcb_lego_box）

| 參數 | 預設值 | 說明 |
|------|--------|------|
| PCB_L / PCB_W | 48 / 24 mm | 線路板尺寸 |
| BOX_D | 10 mm | 盒深 |
| WALL | 2 mm | 壁厚 |
| CLEAR | 0.3 mm | 每邊間隙 |
| CLIP_OVH | 1.0 mm | 卡扣咬住 PCB 的距離 |
| LEGO_ROWS / COLS | 3 × 3 | 背面樂高孔排列 |

## 列印建議

- 材質：**PETG**（卡扣需要彈性；PLA 可能在 snap 時斷裂）
- 層高：0.2mm
- 填充：20%
- 支撐：不需要（開口朝上列印）
