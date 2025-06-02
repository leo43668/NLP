import json

# Ruta del notebook 
ruta = "/content/Version_Final_how_to_track_and_count_vehicles_with_yolov11.ipynb"  # cambia esto

# Cargar el notebook como JSON
with open(ruta, "r", encoding="utf-8") as f:
    data = json.load(f)

# Limpia los widgets si están dañados
if "widgets" in data.get("metadata", {}):
    print("Corrigiendo metadata.widgets...")
    del data["metadata"]["widgets"]

# Guardar el notebook limpio
with open(ruta, "w", encoding="utf-8") as f:
    json.dump(data, f, indent=1)

print("Notebook corregido y guardado.")
