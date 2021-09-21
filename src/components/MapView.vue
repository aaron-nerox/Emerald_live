<template>
  <div ref="map"></div>
</template>

<script>

import { Loader } from "@googlemaps/js-api-loader";


export default {
    name: "TheXMap",
    props:{
        ApiKey: String,
        zoom: Number,
        DefaultUi: Boolean,
        CenterCoords: Object
    },
    async mounted(){
        const loader = new Loader({
        apiKey: this.ApiKey,
        version: "weekly",
        });

        loader.load().then(() => {
        new window.google.maps.Map(this.$refs["map"], {
            center: this.CenterCoords,
            zoom: this.zoom,
            disableDefaultUI: !this.DefaultUi,
            styles: [
        {
        "elementType": "geometry",
        "stylers": [
            {
            "color": "#f5f5f5"
            }
        ]
        },
        {
        "elementType": "labels.icon",
        "stylers": [
            {
            "visibility": "off"
            }
        ]
        },
        {
        "elementType": "labels.text.fill",
        "stylers": [
            {
            "color": "#616161"
            }
        ]
        },
        {
        "elementType": "labels.text.stroke",
        "stylers": [
            {
            "color": "#f5f5f5"
            }
        ]
        },
        {
        "featureType": "administrative.country",
        "elementType": "geometry.stroke",
        "stylers": [
            {
            "color": "#6e6e6e"
            }
        ]
        },
        {
        "featureType": "administrative.land_parcel",
        "elementType": "labels.text.fill",
        "stylers": [
            {
            "color": "#bdbdbd"
            }
        ]
        },
        {
        "featureType": "administrative.province",
        "elementType": "geometry.stroke",
        "stylers": [
            {
            "color": "#383838"
            }
        ]
        },
        {
        "featureType": "landscape.man_made",
        "elementType": "geometry.fill",
        "stylers": [
            {
            "color": "#f0fbff"
            }
        ]
        },
        {
        "featureType": "landscape.natural.landcover",
        "elementType": "geometry.fill",
        "stylers": [
            {
            "color": "#f2f2f2"
            }
        ]
        },
        {
        "featureType": "poi",
        "stylers": [
            {
            "visibility": "on"
            }
        ]
        },
        {
        "featureType": "poi",
        "elementType": "geometry",
        "stylers": [
            {
            "color": "#eeeeee"
            }
        ]
        },
        {
        "featureType": "poi",
        "elementType": "labels.text.fill",
        "stylers": [
            {
            "color": "#757575"
            }
        ]
        },
        {
        "featureType": "poi.attraction",
        "stylers": [
            {
            "visibility": "on"
            }
        ]
        },
        {
        "featureType": "poi.park",
        "elementType": "geometry",
        "stylers": [
            {
            "color": "#e5e5e5"
            }
        ]
        },
        {
        "featureType": "poi.park",
        "elementType": "labels.text.fill",
        "stylers": [
            {
            "color": "#9e9e9e"
            }
        ]
        },
        {
        "featureType": "road",
        "elementType": "geometry",
        "stylers": [
            {
            "color": "#ffffff"
            }
        ]
        },
        {
        "featureType": "road.arterial",
        "elementType": "labels.text.fill",
        "stylers": [
            {
            "color": "#757575"
            }
        ]
        },
        {
        "featureType": "road.highway",
        "elementType": "geometry",
        "stylers": [
            {
            "color": "#c9c9c9"
            }
        ]
        },
        {
        "featureType": "road.highway",
        "elementType": "labels.text.fill",
        "stylers": [
            {
            "color": "#616161"
            }
        ]
        },
        {
        "featureType": "road.local",
        "elementType": "labels.text.fill",
        "stylers": [
            {
            "color": "#9e9e9e"
            }
        ]
        },
        {
        "featureType": "transit",
        "stylers": [
            {
            "visibility": "on"
            }
        ]
        },
        {
        "featureType": "transit.line",
        "elementType": "geometry",
        "stylers": [
            {
            "color": "#e5e5e5"
            }
        ]
        },
        {
        "featureType": "transit.station",
        "elementType": "geometry",
        "stylers": [
            {
            "color": "#eeeeee"
            }
        ]
        },
        {
        "featureType": "water",
        "elementType": "geometry",
        "stylers": [
            {
            "color": "#c9c9c9"
            }
        ]
        },
        {
        "featureType": "water",
        "elementType": "geometry.fill",
        "stylers": [
            {
            "color": "#00bfff"
            }
        ]
        },
        {
        "featureType": "water",
        "elementType": "labels.text",
        "stylers": [
            {
            "color": "#ffffff"
            },
            {
            "weight": 2.5
            }
        ]
        },
        {
        "featureType": "water",
        "elementType": "labels.text.fill",
        "stylers": [
            {
            "color": "#ffffff"
            }
        ]
        }
            ]
        });
    });
    }
}
</script>

<style>

</style>