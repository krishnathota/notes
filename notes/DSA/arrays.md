# arrays

# DevExtreme 25.2 for Angular — AI Knowledge Base

> **Important:** In MES applications, prefer `dex-mfg-*` ODS components over raw DevExtreme where an ODS equivalent exists. Use DevExtreme directly only when no ODS wrapper is available. See `ui/dex-mfg-*/overview.md`.

---

## Overview

DevExtreme 25.2 is a comprehensive UI component library for Angular 21. It provides \~80 components across data visualization, editing, navigation, scheduling, and layout. All components integrate with Angular's template binding system and are compatible with Angular 21 Signals via reactive bridging (`toSignal`, `toObservable`).

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

ComponentDescriptionSelectorReferenceDataGridFull-featured data table with sorting, filtering, editing, grouping, export`dx-data-grid`references/data/data-grid.mdTreeListHierarchical tree-table hybrid with expand/collapse`dx-tree-list`references/data/tree-list.md

### Charts

ComponentDescriptionSelectorReferenceChartMulti-series 2D chart (line, bar, area, scatter, etc.)`dx-chart`references/charts/chart.mdPieChartPie and donut charts`dx-pie-chart`references/charts/pie-chart.mdFunnelFunnel / pyramid chart`dx-funnel`references/charts/funnel.mdGaugeCircular and linear gauge`dx-circular-gauge` / `dx-linear-gauge`references/charts/gauge.mdSparklineCompact inline mini-chart`dx-sparkline`references/charts/sparkline.mdVectorMapGeographic map visualization`dx-vector-map`references/charts/vector-map.mdSankeySankey flow diagram`dx-sankey`references/charts/sankey.mdTreeMapHierarchical treemap / heatmap`dx-tree-map`references/charts/tree-map.mdRangeSelectorInteractive axis range selector`dx-range-selector`references/charts/range-selector.md

### Editors

ComponentDescriptionSelectorReferenceTextBoxSingle-line text input`dx-text-box`references/editors/text-box.mdNumberBoxNumeric input with spin buttons`dx-number-box`references/editors/number-box.mdDateBoxDate/time picker`dx-date-box`references/editors/date-box.mdSelectBoxSingle-value dropdown select`dx-select-box`references/editors/select-box.mdTagBoxMulti-value tag/chip select`dx-tag-box`references/editors/tag-box.mdLookupMobile-optimized dropdown`dx-lookup`references/editors/lookup.mdCheckBoxBoolean checkbox`dx-check-box`references/editors/check-box.mdSwitchToggle switch`dx-switch`references/editors/switch.mdRadioGroupRadio button group`dx-radio-group`references/editors/radio-group.mdSliderSingle-value range slider`dx-slider`references/editors/slider.mdRangeSliderTwo-handle range slider`dx-range-slider`references/editors/range-slider.mdColorBoxColor picker`dx-color-box`references/editors/color-box.mdHtmlEditorRich text / WYSIWYG editor`dx-html-editor`references/editors/html-editor.md

### Navigation

ComponentDescriptionSelectorReferenceAccordionCollapsible panel group`dx-accordion`references/navigation/accordion.mdTabsTab strip (no associated content panels)`dx-tabs`references/navigation/tabs.mdTabPanelTab strip with associated content panels`dx-tab-panel`references/navigation/tab-panel.mdTreeViewHierarchical tree with checkboxes and selection`dx-tree-view`references/navigation/tree-view.mdMenuHorizontal/vertical menu with submenus`dx-menu`references/navigation/menu.mdContextMenuRight-click context menu`dx-context-menu`references/navigation/context-menu.mdDrawerSlide-out side panel / navigation drawer`dx-drawer`references/navigation/drawer.mdToolbarAction toolbar with overflow`dx-toolbar`references/navigation/toolbar.mdScrollViewScrollable container with pull-to-refresh`dx-scroll-view`references/navigation/scroll-view.mdBoxFlexbox-style layout container`dx-box`references/navigation/box.mdResponsiveBoxBreakpoint-responsive layout grid`dx-responsive-box`references/navigation/responsive-box.md

### Overlays

ComponentDescriptionSelectorReferencePopupModal dialog / popup window`dx-popup`references/overlays/popup.mdPopoverAnchored popover balloon`dx-popover`references/overlays/popover.mdToastAuto-dismiss notification`dx-toast`references/overlays/toast.mdLoadPanelFull-area loading overlay`dx-load-panel`references/overlays/load-panel.mdLoadIndicatorInline spinner indicator`dx-load-indicator`references/overlays/load-indicator.md

### Scheduling

ComponentDescriptionSelectorReferenceSchedulerFull calendar / appointment scheduler`dx-scheduler`references/scheduling/scheduler.mdCalendarMonth-view date picker calendar`dx-calendar`references/scheduling/calendar.mdDateRangeBoxDual date-input range picker`dx-date-range-box`references/scheduling/date-range-box.md

### Collections

ComponentDescriptionSelectorReferenceListScrollable item list with selection, grouping, drag-sort`dx-list`references/collections/list.mdTileViewGrid of tile cards`dx-tile-view`references/collections/tile-view.mdGalleryImage/item carousel`dx-gallery`references/collections/gallery.md

### Utilities

ComponentDescriptionSelectorReferenceMapInteractive map (Google/Bing/Azure)`dx-map`references/utilities/map.mdFileManagerFile explorer UI`dx-file-manager`references/utilities/file-manager.mdFileUploaderFile upload with drag-drop`dx-file-uploader`references/utilities/file-uploader.md

### Forms

ComponentDescriptionSelectorReferenceFormStructured form with labels, groups, validation`dx-form`references/forms/form.mdValidatorAttaches validation rules to an editor`dx-validator`references/forms/validator.mdValidationGroupGroups validators for batch validation`dx-validation-group`references/forms/validation-group.mdValidationSummaryDisplays all validation errors`dx-validation-summary`references/forms/validation-summary.md

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

Use caseAPITwo-way bindable input (child component you own)`model()`Local reactive state`signal()`Derived/read-only value`computed()`Side effects on state change`effect()`

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

CategorySSR SafeNotesDataGrid, TreeListNoUse `isPlatformBrowser` guardAll ChartsNoCanvas/SVG rendering requires browserAll EditorsPartialRender shell; no interactive initPopup, DrawerNoDOM positioning requires browserToast, LoadPanelNoBrowser-onlySchedulerNoComplex DOM layoutForm, ValidatorYesRender markup safelyBox, ResponsiveBoxYesPure layout

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