# Color Palette — egui Color Picker

Episode 12 of the **Learn egui in Neovim** series.

A color palette app where you pick colors with a visual editor, save them to a collection, and see each swatch rendered with its hex code.

## What You'll Learn

- `ui.color_edit_button_rgb()` for an interactive color picker widget
- `egui::Color32` and `egui::Rgba` for color representation
- `ui.allocate_exact_size()` and `ui.painter().rect_filled()` to draw custom color swatches
- Hex color formatting with `{:02X}`
- Deferred removal with `Option<usize>` to safely remove items during iteration

## Run

```bash
cargo run
```

## Key Code

```rust
ui.color_edit_button_rgb(&mut self.current_color);

if ui.button("Save Color").clicked() {
    self.saved_colors.push(self.current_color);
}

// Draw a color swatch
let (rect, _response) = ui.allocate_exact_size(
    egui::vec2(40.0, 20.0),
    egui::Sense::hover(),
);
ui.painter().rect_filled(rect, 4.0, c);

ui.label(format!("#{:02X}{:02X}{:02X}", c.r(), c.g(), c.b()));
```

## Series

This is part of the [Learn egui in Neovim](https://www.youtube.com/@CelesteAI) series, where we build Rust GUI apps step by step.
