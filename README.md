// app.js
let cutsList = document.getElementById("cutsList");
let map;

// Inicializa el mapa de Google Maps
function initMap() {
  map = new google.maps.Map(document.getElementById("map"), {
    center: { lat: -34.397, lng: 150.644 },
    zoom: 8,
  });
}

// Función para registrar un corte de agua
document.getElementById("waterCutForm").addEventListener("submit", function (event) {
  event.preventDefault();

  // Obtener valores del formulario
  let location = document.getElementById("location").value;
  let startTime = document.getElementById("startTime").value;
  let endTime = document.getElementById("endTime").value || "No especificado";
  let cause = document.getElementById("cause").value;

  // Agregar corte de agua a la lista
  let cutItem = document.createElement("li");
  cutItem.innerHTML = `<strong>Ubicación:</strong> ${location} <br>
                       <strong>Inicio:</strong> ${startTime} <br>
                       <strong>Fin:</strong> ${endTime} <br>
                       <strong>Causa:</strong> ${cause}`;
  cutsList.appendChild(cutItem);

  // Resetear el formulario
  document.getElementById("waterCutForm").reset();
});
