Vibe Coded with significant help from Gemini 2.5 Pro
NetJS. (2025). Interactive Network Map [Computer software]. GitHub. https://buddyledger.github.io/NetJS/

# Interactive Network Map: User Manual

This document provides a guide on how to use the interactive network map tool, which allows you to create, visualize, and manage relationships between entities (referred to as "People" or "Nodes").

## 1. Overview

The tool provides an interactive canvas to build network diagrams. You can define people, their departments (groups), roles, and the relationships between them. The appearance, physics, and data can be customized, saved, and loaded.

## 2. Main Interface Components

The interface is divided into three main areas:
* **Main Control Buttons (Header):** For global actions like saving, loading, and exporting.
* **Sidebar:** For editing data, defining types, viewing lists, and adjusting settings.
* **Main Content Area:** Displays the interactive network map and its legend.

## 3. Main Control Buttons (Header)

Located at the top of the page, these buttons provide core functionalities:

* **Save JSON:** Saves the current diagram, including all node positions, custom types (groups, roles, relationships), and settings, into a JSON file. This is the recommended format for saving your work with full fidelity.
* **Load JSON:** Loads a previously saved network diagram from a JSON file, replacing the current diagram.
* **Save Text:** Saves a simplified version of the diagram data (nodes, edges, and type definitions) into a plain text file. This format does not include visual details like node positions or advanced settings.
* **Load Text:** Loads a network diagram from a text file. Note that this will only load basic node/edge information and type definitions.
* **Export Image with Legend:** Captures the current network diagram along with its legend and saves it as a PNG image file.
* **Clear Diagram:** Removes all people (nodes) and relationships (edges) from the current diagram. Custom-defined groups, roles, and relationship types will remain.
* **Reset Diagram:** Resets the entire application to its default state. This will clear all current data, including custom-defined groups, roles, and relationship types, and load a default sample dataset.

## 4. Sidebar

The sidebar is organized into tabs, allowing you to manage different aspects of your network map.

### 4.1. Edit Tab

This is the primary tab for building your network.

* **Add/Edit Person (Node):**
    * **Name/Label:** Enter the name of the person.
    * **Department/Group:** Assign the person to a pre-defined department (see Define Tab).
    * **Role:** Assign a role to the person (see Define Tab).
    * **Add Person/Update Button:** Click to add a new person or save changes if editing an existing one.
    * **Cancel Edit Button:** Appears when editing; click to discard changes.
* **Add/Edit Relationship (Edge):**
    * **From Person:** Select the starting person for the relationship.
    * **To Person:** Select the target person for the relationship.
    * **Relationship Type:** Choose the type of relationship (e.g., "Reports To", "Collaborators"). These are defined in the Define Tab.
    * **Strength (Width/Physics):** Set the visual strength/thickness of the relationship line (Weak, Medium, Strong).
    * **Override Controls:**
        * **Arrow From/Arrow To:** Manually set the direction of arrows, overriding the default for the chosen relationship type.
        * **Show Label:** Manually choose whether to display the relationship type's label on the diagram for this specific edge.
    * **Add Relationship/Update Relationship Button:** Click to add a new relationship or save changes if editing.
    * **Cancel Edit Button:** Appears when editing; click to discard changes.

### 4.2. Define Tab

This tab allows you to customize the types used in your network diagram.

* **New/Edit Group Type (Node Departments):**
    * **Group Display Name:** The name of the department or group (e.g., "Sales", "Engineering").
    * **Group Color:** The fill color used for nodes belonging to this group.
    * **Add Group Type/Update Group Type Button:** Saves the new or edited group type.
* **New/Edit Role Type (Node Roles):**
    * **Role Display Name:** The name of the role (e.g., "Manager", "Developer").
    * **Role Outline Color:** The border color used for nodes assigned this role.
    * **Node Shape:** The shape used for nodes assigned this role (e.g., Circle, Box, Diamond).
    * **Add Role Type/Update Role Type Button:** Saves the new or edited role type.
* **New/Edit Relationship Type:**
    * **Type Display Label:** The name of the relationship (e.g., "Advises", "Mentors").
    * **Type Color:** The color of the line representing this relationship.
    * **Default Arrow Style:** Choose the default arrow direction (None, Directional A → B, Bi-Directional A ↔ B).
    * **Show label on diagram by default:** Check if the label for this relationship type should be visible on edges by default.
    * **Label Position (if shown):** If the label is shown, select its position relative to the edge (Middle, Top, Bottom, Horizontal).
    * **Add Relationship Type/Update Relationship Type Button:** Saves the new or edited relationship type.

### 4.3. Lists Tab

This tab provides an overview of the current data in your diagram and your defined types. Each list can be expanded or collapsed.

* **Current People:** Lists all people (nodes) added to the diagram. You can edit or delete them from here.
* **Current Relationships:** Lists all relationships (edges) defined. You can edit or delete them from here.
* **Manage Node Groups:** Lists all defined node groups (departments). You can edit or delete them.
* **Manage Node Roles:** Lists all defined node roles. You can edit or delete them.
* **Manage Relationship Types:** Lists all defined relationship types. You can edit or delete them.

### 4.4. Settings Tab

This tab allows you to fine-tune the physics simulation and visual appearance of the network.

* **Physics:**
    * **Enable Physics:** Toggle the physics engine on or off. When off, nodes can be manually dragged and will stay in place.
    * **Spring Stiffness:** Controls the stiffness of the "springs" (edges).
    * **Central Gravity:** The force pulling nodes towards the center of the canvas.
    * **Node Repulsion:** How much nodes push each other away.
    * **Ideal Spring Length:** The desired length for edges.
    * **Damping (Friction):** How quickly the network settles down.
    * **Apply Physics Button:** Applies the changed physics settings.
* **Appearance:**
    * **Edge Curve Factor (Parallel):** Controls how much parallel edges between the same two nodes curve away from each other.
    * **Edge Smooth Type:** The style of curve for edges (e.g., Dynamic, Continuous, Curved CW/CCW).
    * **Smooth Roundness:** (Applies to certain smooth types) Controls the roundness of the curve.
    * **Node Size:** The default size for nodes.
    * **Node Font Size:** The font size for node labels.
    * **Edge Base Width:** The default thickness for edge lines (strength settings are multipliers of this).
    * **Apply Appearance Button:** Applies the changed appearance settings.

## 5. Main Content Area

* **Network Display (`mynetwork`):**
    This is the main canvas where your interactive network diagram is displayed.
    * **Interaction:** You can typically drag nodes (if physics is enabled, they will try to resettle), zoom in/out, and pan the view. Hovering over nodes or edges may show tooltips with more information.
    * **Selection:** Clicking on a node or edge might select it for editing (details would then appear in the "Edit" tab in the sidebar).
* **Legend (`legendContainer`):**
    Displayed to the right of the network, the legend helps interpret the diagram:
    * **Node Departments (Fill):** Shows the fill color associated with each defined Node Group/Department.
    * **Node Roles (Shape & Outline):** Shows the shape and outline color associated with each defined Node Role.
    * **Relationship Types (Color):** Shows the line color associated with each defined Relationship Type.

## 6. Basic Workflow

1.  **Define Types (Optional but Recommended):**
    * Go to the **Define Tab**.
    * Create Node Groups (e.g., "Marketing", "HR") with distinct colors.
    * Create Node Roles (e.g., "Team Lead", "Analyst") with distinct outline colors and shapes.
    * Create Relationship Types (e.g., "Manages", "Works With") with distinct colors and default arrow styles.
2.  **Add People (Nodes):**
    * Go to the **Edit Tab**.
    * In the "Add/Edit Person" section, enter the person's name.
    * Select their Department (Group) and Role from the dropdowns.
    * Click "Add Person".
3.  **Add Relationships (Edges):**
    * Go to the **Edit Tab**.
    * In the "Add/Edit Relationship" section, select the "From Person" and "To Person".
    * Choose the "Relationship Type".
    * Adjust "Strength" and override arrow/label visibility if needed.
    * Click "Add Relationship".
4.  **Customize & View:**
    * Use the **Settings Tab** to adjust physics for layout or visual appearance.
    * Use the **Lists Tab** to review your data.
    * Refer to the **Legend** to understand the visual cues.
5.  **Save Your Work:**
    * Use the **Save JSON** button in the header to save all your data and settings.
6.  **Export:**
    * Use the **Export Image with Legend** button to get a PNG image of your diagram.

## 7. Important Notes

* **Underlying Libraries:** This tool utilizes the `vis.js` library for network visualization and `html2canvas` for the image export functionality.
* **Data Persistence:** Your work is not automatically saved. Always use the "Save JSON" or "Save Text" buttons to avoid losing data. JSON is preferred for retaining all visual and structural information.
* **Default Dataset:** When the page is first loaded or when "Reset Diagram" is used, a small sample dataset is loaded to demonstrate functionality.
* **Editing from Lists:** You can also initiate editing or deletion of nodes, edges, and defined types directly from the respective lists in the "Lists" tab.
* **Browser Console:** For troubleshooting or deeper understanding, the browser's developer console may log actions and errors.

This manual should help you get started with the Interactive Network Map tool. Experiment with the different features to fully explore its capabilities.
