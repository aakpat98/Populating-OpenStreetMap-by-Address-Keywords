# Populating OpenStreetMap with User-Specified Addresses

This project demonstrates how to populate OpenStreetMap with user-specified addresses, using universities as an example. The code can be customized to accept any address.

## Overview

The project utilizes the OpenStreetMap API to convert user-entered addresses into geographical locations and visualizes them on a map. It involves reading input addresses, geocoding them to obtain latitude and longitude, storing the data in a SQLite database, and generating a visual representation using OpenStreetMap.

## Repository Structure

- **Python Scripts:**
  - `geoload.py`: Reads input addresses, checks if they are already in the database, and if not, retrieves geocoded data from the OpenStreetMap API and stores it in `opengeo.sqlite`.
  - `geodump.py`: Reads the database and writes the geocoded data to `where.js` in a format suitable for visualization.

- **Data Files:**
  - `where.data`: Contains the list of addresses to be geocoded.
  - `opengeo.sqlite`: SQLite database storing the geocoded information.

- **Visualization Files:**
  - `where.js`: JavaScript file containing the geocoded data for visualization.
  - `where.html`: HTML file that uses OpenLayers to display the map with the geocoded locations.

## Setup and Usage

**Prepare the Input Data:**

   Edit the `where.data` file to include the addresses you wish to geocode, with each address on a new line.

**Load and Geocode Addresses:**

   Run the `geoload.py` script to read the addresses from `where.data`, check if they are already in the database, and retrieve geocoded data for new addresses:

   ```bash
   python geoload.py
   ```

**Generate Visualization Data:**

   After geocoding, run the `geodump.py` script to read the database and write the geocoded data to `where.js`:

   ```bash
   python geodump.py
   ```

**View the Map:**

   Open `where.html` in a web browser to visualize the geocoded addresses on an interactive map.

## Customization

To customize the project for different types of addresses:

- **Input Data:** Modify the `where.data` file to include your desired addresses.

- **Geocoding Parameters:** Adjust the `geoload.py` script if necessary to handle specific geocoding requirements or API parameters.

---

By following this guide, you can geocode user-specified addresses and visualize them on OpenStreetMap, facilitating the mapping of various locations based on user input. 
