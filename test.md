# Categorizing WiFi Hotspots by Distance in PowerBI

## Step 1: Create Distance Categories
# In PowerBI, create a new column to categorize distances based on the "Distance to nearest Public Wi-Fi Hotspot (km)" field.

## Step 2: Use Power Query Editor
# Open the Power Query Editor from the Home tab by selecting "Transform Data".
# In the "Add Column" tab, create a new custom column with the following if-else logic:

# if [Distance to nearest Public Wi-Fi Hotspot (km)] <= 0.5 then "Very Close"
# else if [Distance to nearest Public Wi-Fi Hotspot (km)] <= 1 then "Close"
# else if [Distance to nearest Public Wi-Fi Hotspot (km)] <= 2 then "Moderate"
# else "Far"

# Close the Power Query Editor and apply changes.

## Step 3: Update Your Chart
# In the line chart visualization, drag the new distance category column to the X-axis field.
# The Y-axis should represent the count or average of hours spent gaming.

## Step 4: Adjust Visual Elements
# Update axis titles and labels to reflect the new distance categorization.
# Modify text sizes and chart elements for better readability.
