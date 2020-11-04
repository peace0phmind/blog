---
title: "Blender 2.8x快捷键"
date: 2020-11-02T12:08:35+08:00
draft: true
---

本文主要记录[Blender](https://www.blender.org/)2.8x的快捷方式。

注：`num_`做前缀的按钮表示数字键盘区的按键，`num_7`表示的是`数字小键盘7`，其他对照类比。普通的按键`7`会直接用`7`标识。`lmb`表示鼠标左键，`rmb`表示鼠标右键，`mmb`表示鼠标中键。

## 设置单位
blender 2.28默认单位为m,需要设置为mm, Unit Scale需要甚至为0.001.

## 通用快捷键
* `shift-a` show add menu
* `shift-s-1` cursor to world origin
* `shift-s-2` cursor to selected
* `shift-s-3` cursor to active
* `shift-s-4` cursor to gride
* `shift-s-6` selection to grid
* `shift-s-7` selection to cursor (keep offset)
* `shift-s-8` selection to cursor
* `shift-s-9` selection to active
* `x-d` remove object
* `ctrl-lmb` Lasso select: drag the mouse to form a freehand selection area.


## 视角切换
* `num_7` Top View
* `ctrl-num_7` Bottom View
* `num_1` Front View
* `ctrl-num_1` Back View
* `num_3` Right View
* `ctrl-num_3` Left View
* `num_0` Camera View
* `num_.` Put select objects to the view center.(select object, move mouse to view, press `num_.` button)
* `shift-mmb` move view


## 对象模式（已选择物体）
* `tab` Start/stop EditMode.
* `alt-e`. Start/stop EditMode. Alternative hotkey: `tab`.
* `s` size(scale) mode
* `r` rotate mode 
* `a` select all
* `aa` deselect all
* `home` see all object in one view
* `shift-c` CentreZero View. The 3DCursor is set to zero (0,0,0) and the view is changed so that all Objects, including the 3Dcursor, can be displayed. This is an alternative for `home`.
* `shift-d`. Add Duplicate. The selected Objects are duplicated. Grab mode starts immediately thereafter.
* `alt-g`. Clears translations, given in Grab mode. The X,Y,Z locations of selected Objects are set to zero.
* `alt-j`. Join faces, selected triangular faces are joined in pairs
and transformed to quads
* `z-4` wireframe mode
* `z-6` solid mode
* `z-8` rendered mode
* `z-2` material preview
* `shift-z` toggles shaded mode on/off
* `alt-z` toggles textured mode on/off
* `alt-s` Clears size. The X,Y,Z dimensions of selected Objects
are set to 1.0.
* `ctrl-m` mirror menu.
* `alt-o` Clear Origin. The ‘Origin’ is erased for all Child
Objects, which causes the Child Objects to move to the exact
location of the Parent Objects.
* `m` Moves selected Object(s) to another layer, a pop-up appers.
* `g` Grab Mode.
* `g-x` `g-y` `g-z` constrains movement to X, Y or Z axis of the global reference.


## 编辑模式（mesh）
* `e` extrude selected
* `e-x` `e-y` `e-z` constrains extrude selected to X, Y or Z axis of the global reference.
* `a` select all
* `a-a` deselect all
* `alt-lmb` select a collection of points
* `f` Make Edge/Face. If 2 vertices are selected, an edge is
created. If 3 or 4 vertices are selected, a face is created.
* `shift-f` Fill selected. All selected vertices that are bound by
edges and form a closed polygon are filled with triangular faces.
Holes are automatically taken into account. This operation is 2D;
various layers of polygons must be filled in succession.
* `alt-f` Beauty Fill. The edges of all the selected triangular faces
are switched in such a way that equally sized faces are formed.
This operation is 2D; various layers of polygons must be filled in
succession. The Beauty Fill can be performed immediately after
a Fill.
* `ctrl-f` Flip faces, selected triangular faces are paired and
common edge of each pair swapped.
* `ctrl-r` Face Loop Cut.Face loops are highlighted starting from edge under mouse pointer.
* `alt-m` select multiple points and merge them
* `shift-c` CentreZero View. The 3DCursor is set to zero (0,0,0) and the view is changed so that all Objects, including the 3Dcursor, can be displayed. This is an alternative for `home`.
* `o` Switch in/out of Proportional Editing.
* `shift-g` Select Similar
* `ctrl-e` edge menu.(include bridge edge loops)
* `shift-n` and `shift-ctrl-n` recalculate the normals of selected faces 
* `ctrl-b` bevel tool


## 参考
[Blender HotKeys In-depth Reference](https://download.blender.org/documentation/BlenderHotkeyReference.pdf)
[blender-2-8-where-is-the-remove-doubles](https://www.blender3darchitect.com/modeling-for-architecture/blender-2-8-where-is-the-remove-doubles/)

[blender-2-8-for-architecture](https://www.blender3darchitect.com/blender-2-8-for-architecture/?source=post)
