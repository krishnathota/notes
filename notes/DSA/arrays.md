# arrays


# DevExtreme 25.2 for Angular — AI Knowledge Base

> **Important:** In MES applications, prefer `dex-mfg-*` ODS components over raw DevExtreme where an ODS equivalent exists. Use DevExtreme directly only when no ODS wrapper is available. See `ui/dex-mfg-*/overview.md`.

---

## Overview

DevExtreme 25.2 is a comprehensive UI component library for Angular 21. It provides ~80 components across data visualization, editing, navigation, scheduling, and layout. All components integrate with Angular's template binding system and are compatible with Angular 21 Signals via reactive bridging (`toSignal`, `toObservable`).

**Key facts:**
- Import via `devextreme-angular` npm package
- Import each component individually: `DxXxxComponent` from `'devextreme-angular/ui/<name>'`
- Components expose properties via `[property]` binding and events via `(onEventName)` binding
- No native Angular Signal inputs — bridge using `toSignal()` / computed values in templates
- Full zoneless support with `provideExperimentalZonelessChangeDetection()`
- SSR: most components are browser-only; use `isPlatformBrowser` guards

---

## Component Index

### Data

| Component | Description | Selector | Reference |
|---|---|---|---|
| DataGrid | Full-featured data table with sorting, filtering, editing, grouping, export | `dx-data-grid` | [references/data/data-grid.md](references/data/data-grid.md) |
| TreeList | Hierarchical tree-table hybrid with expand/collapse | `dx-tree-list` | [references/data/tree-list.md](references/data/tree-list.md) |

### Charts

| Component | Description | Selector | Reference |
|---|---|---|---|
| Chart | Multi-series 2D chart (line, bar, area, scatter, etc.) | `dx-chart` | [references/charts/chart.md](references/charts/chart.md) |
| PieChart | Pie and donut charts | `dx-pie-chart` | [references/charts/pie-chart.md](references/charts/pie-chart.md) |
| Funnel | Funnel / pyramid chart | `dx-funnel` | [references/charts/funnel.md](references/charts/funnel.md) |
| Gauge | Circular and linear gauge | `dx-circular-gauge` / `dx-linear-gauge` | [references/charts/gauge.md](references/charts/gauge.md) |
| Sparkline | Compact inline mini-chart | `dx-sparkline` | [references/charts/sparkline.md](references/charts/sparkline.md) |
| VectorMap | Geographic map visualization | `dx-vector-map` | [references/charts/vector-map.md](references/charts/vector-map.md) |
| Sankey | Sankey flow diagram | `dx-sankey` | [references/charts/sankey.md](references/charts/sankey.md) |
| TreeMap | Hierarchical treemap / heatmap | `dx-tree-map` | [references/charts/tree-map.md](references/charts/tree-map.md) |
| RangeSelector | Interactive axis range selector | `dx-range-selector` | [references/charts/range-selector.md](references/charts/range-selector.md) |

### Editors

| Component | Description | Selector | Reference |
|---|---|---|---|
| TextBox | Single-line text input | `dx-text-box` | [references/editors/text-box.md](references/editors/text-box.md) |
| NumberBox | Numeric input with spin buttons | `dx-number-box` | [references/editors/number-box.md](references/editors/number-box.md) |
| DateBox | Date/time picker | `dx-date-box` | [references/editors/date-box.md](references/editors/date-box.md) |
| SelectBox | Single-value dropdown select | `dx-select-box` | [references/editors/select-box.md](references/editors/select-box.md) |
| TagBox | Multi-value tag/chip select | `dx-tag-box` | [references/editors/tag-box.md](references/editors/tag-box.md) |
| Lookup | Mobile-optimized dropdown | `dx-lookup` | [references/editors/lookup.md](references/editors/lookup.md) |
| CheckBox | Boolean checkbox | `dx-check-box` | [references/editors/check-box.md](references/editors/check-box.md) |
| Switch | Toggle switch | `dx-switch` | [references/editors/switch.md](references/editors/switch.md) |
| RadioGroup | Radio button group | `dx-radio-group` | [references/editors/radio-group.md](references/editors/radio-group.md) |
| Slider | Single-value range slider | `dx-slider` | [references/editors/slider.md](references/editors/slider.md) |
| RangeSlider | Two-handle range slider | `dx-range-slider` | [references/editors/range-slider.md](references/editors/range-slider.md) |
| ColorBox | Color picker | `dx-color-box` | [references/editors/color-box.md](references/editors/color-box.md) |
| HtmlEditor | Rich text / WYSIWYG editor | `dx-html-editor` | [references/editors/html-editor.md](references/editors/html-editor.md) |

### Navigation

| Component | Description | Selector | Reference |
|---|---|---|---|
| Accordion | Collapsible panel group | `dx-accordion` | [references/navigation/accordion.md](references/navigation/accordion.md) |
| Tabs | Tab strip (no associated content panels) | `dx-tabs` | [references/navigation/tabs.md](references/navigation/tabs.md) |
| TabPanel | Tab strip with associated content panels | `dx-tab-panel` | [references/navigation/tab-panel.md](references/navigation/tab-panel.md) |
| TreeView | Hierarchical tree with checkboxes and selection | `dx-tree-view` | [references/navigation/tree-view.md](references/navigation/tree-view.md) |
| Menu | Horizontal/vertical menu with submenus | `dx-menu` | [references/navigation/menu.md](references/navigation/menu.md) |
| ContextMenu | Right-click context menu | `dx-context-menu` | [references/navigation/context-menu.md](references/navigation/context-menu.md) |
| Drawer | Slide-out side panel / navigation drawer | `dx-drawer` | [references/navigation/drawer.md](references/navigation/drawer.md) |
| Toolbar | Action toolbar with overflow | `dx-toolbar` | [references/navigation/toolbar.md](references/navigation/toolbar.md) |
| ScrollView | Scrollable container with pull-to-refresh | `dx-scroll-view` | [references/navigation/scroll-view.md](references/navigation/scroll-view.md) |
| Box | Flexbox-style layout container | `dx-box` | [references/navigation/box.md](references/navigation/box.md) |
| ResponsiveBox | Breakpoint-responsive layout grid | `dx-responsive-box` | [references/navigation/responsive-box.md](references/navigation/responsive-box.md) |

### Overlays

| Component | Description | Selector | Reference |
|---|---|---|---|
| Popup | Modal dialog / popup window | `dx-popup` | [references/overlays/popup.md](references/overlays/popup.md) |
| Popover | Anchored popover balloon | `dx-popover` | [references/overlays/popover.md](references/overlays/popover.md) |
| Toast | Auto-dismiss notification | `dx-toast` | [references/overlays/toast.md](references/overlays/toast.md) |
| LoadPanel | Full-area loading overlay | `dx-load-panel` | [references/overlays/load-panel.md](references/overlays/load-panel.md) |
| LoadIndicator | Inline spinner indicator | `dx-load-indicator` | [references/overlays/load-indicator.md](references/overlays/load-indicator.md) |

### Scheduling

| Component | Description | Selector | Reference |
|---|---|---|---|
| Scheduler | Full calendar / appointment scheduler | `dx-scheduler` | [references/scheduling/scheduler.md](references/scheduling/scheduler.md) |
| Calendar | Month-view date picker calendar | `dx-calendar` | [references/scheduling/calendar.md](references/scheduling/calendar.md) |
| DateRangeBox | Dual date-input range picker | `dx-date-range-box` | [references/scheduling/date-range-box.md](references/scheduling/date-range-box.md) |

### Collections

| Component | Description | Selector | Reference |
|---|---|---|---|
| List | Scrollable item list with selection, grouping, drag-sort | `dx-list` | [references/collections/list.md](references/collections/list.md) |
| TileView | Grid of tile cards | `dx-tile-view` | [references/collections/tile-view.md](references/collections/tile-view.md) |
| Gallery | Image/item carousel | `dx-gallery` | [references/collections/gallery.md](references/collections/gallery.md) |

### Utilities

| Component | Description | Selector | Reference |
|---|---|---|---|
| Map | Interactive map (Google/Bing/Azure) | `dx-map` | [references/utilities/map.md](references/utilities/map.md) |
| FileManager | File explorer UI | `dx-file-manager` | [references/utilities/file-manager.md](references/utilities/file-manager.md) |
| FileUploader | File upload with drag-drop | `dx-file-uploader` | [references/utilities/file-uploader.md](references/utilities/file-uploader.md) |

### Forms

| Component | Description | Selector | Reference |
|---|---|---|---|
| Form | Structured form with labels, groups, validation | `dx-form` | [references/forms/form.md](references/forms/form.md) |
| Validator | Attaches validation rules to an editor | `dx-validator` | [references/forms/validator.md](references/forms/validator.md) |
| ValidationGroup | Groups validators for batch validation | `dx-validation-group` | [references/forms/validation-group.md](references/forms/validation-group.md) |
| ValidationSummary | Displays all validation errors | `dx-validation-summary` | [references/forms/validation-summary.md](references/forms/validation-summary.md) |

---

## Quick Start — Angular 21 Standalone

```typescript
import { Component, signal, computed } from '@angular/core';
import { DxDataGridComponent } from 'devextreme-angular/ui/data-grid';

@Component({
  selector: 'app-quick-start',
  imports: [DxDataGridComponent],
  template: `
    <dx-data-grid
      [dataSource]="rows()"
      [showBorders]="true"
      [columnAutoWidth]="true"
      (onSelectionChanged)="onSelect($event)"
    />
  `
})
export class QuickStartComponent {
  rows = signal([
    { id: 1, name: 'Work Order 1001', status: 'Open'   },
    { id: 2, name: 'Work Order 1002', status: 'Closed' },
  ]);

  onSelect(e: any): void {
    console.log('Selected:', e.selectedRowsData);
  }
}
```

---

## Global Patterns

### Named Config Components

DevExtreme v25 introduces named configuration components to replace generic `dxo-`/`dxi-` components. Use named forms in all new code:

- Use `dxi-data-grid-column` not `dxi-column`
- Use `dxo-data-grid-pager` not `dxo-pager`
- Use `dxi-toolbar-item` not `dxi-item` (inside `dx-toolbar`)
- Use `dxi-form-item` not `dxi-item` (inside `dx-form`)
- Use `dxi-context-menu-item` not `dxi-item` (inside `dx-context-menu`)

Every named config component used in a template must be imported explicitly in `@Component.imports`. Import from the widget-specific nested path:

```typescript
import {
  DxiDataGridColumnComponent,
  DxoDataGridPagerComponent,
  DxoDataGridPagingComponent,
} from 'devextreme-angular/ui/data-grid/nested';

import { DxiTreeListColumnComponent } from 'devextreme-angular/ui/tree-list/nested';
import { DxiFormItemComponent } from 'devextreme-angular/ui/form/nested';
import { DxiToolbarItemComponent } from 'devextreme-angular/ui/toolbar/nested';
import { DxiContextMenuItemComponent } from 'devextreme-angular/ui/context-menu/nested';
```

Naming rule: kebab-case selector → PascalCase + `Component`
- `dxi-data-grid-column` → `DxiDataGridColumnComponent`
- `dxo-data-grid-pager` → `DxoDataGridPagerComponent`

### Signals with DevExtreme

DevExtreme components do not consume Angular Signals natively. Pass signal values using `()` invocation in templates:

```typescript
// Component
filter = signal<string>('Open');
filteredRows = computed(() =>
  this.allRows().filter(r => r.status === this.filter())
);
```

```html
<!-- Template -->
<dx-data-grid [dataSource]="filteredRows()" />
```

### When to use `model()` vs `signal()`

| Use case | API |
|---|---|
| Two-way bindable input (child component you own) | `model()` |
| Local reactive state | `signal()` |
| Derived/read-only value | `computed()` |
| Side effects on state change | `effect()` |

### Bridging RxJS Observables to Signals

```typescript
import { toSignal } from '@angular/core/rxjs-interop';
import { inject } from '@angular/core';

export class MyComponent {
  private svc = inject(DataService);

  // Observable → Signal (auto-unsubscribes)
  rows = toSignal(this.svc.getRows$(), { initialValue: [] });
}
```

### Event Handling with `output()`

DevExtreme emits events via `(onEventName)` template binding. In your own components exposing DevExtreme-backed state:

```typescript
// Your component
rowSelected = output<RowData>();

onGridSelect(e: any): void {
  this.rowSelected.emit(e.selectedRowsData[0]);
}
```

### inject() pattern (preferred over constructor injection)

```typescript
export class MyComponent {
  private router = inject(Router);
  private store  = inject(MyStore);
}
```

---

## Zoneless Summary

DevExtreme 25.2 is compatible with `provideExperimentalZonelessChangeDetection()`. All components use `ChangeDetectorRef.markForCheck()` internally. In zoneless mode:

- All events trigger change detection automatically via Angular's scheduler
- Use `signal()` for all mutable state — avoid plain class properties for template-bound data
- `effect()` with `untracked()` for side effects that should not re-run on every signal change

```typescript
bootstrapApplication(AppComponent, {
  providers: [provideExperimentalZonelessChangeDetection()]
});
```

---

## SSR Summary

| Category | SSR Safe | Notes |
|---|---|---|
| DataGrid, TreeList | No | Use `isPlatformBrowser` guard |
| All Charts | No | Canvas/SVG rendering requires browser |
| All Editors | Partial | Render shell; no interactive init |
| Popup, Drawer | No | DOM positioning requires browser |
| Toast, LoadPanel | No | Browser-only |
| Scheduler | No | Complex DOM layout |
| Form, Validator | Yes | Render markup safely |
| Box, ResponsiveBox | Yes | Pure layout |

```typescript
import { isPlatformBrowser, PLATFORM_ID } from '@angular/common';
import { inject } from '@angular/core';

export class MyComponent {
  private platformId = inject(PLATFORM_ID);
  isBrowser = isPlatformBrowser(this.platformId);
}
```

```html
<dx-data-grid *ngIf="isBrowser" [dataSource]="rows()" />
```
