# CS 4331 - Project #1

## Moon House

![Main Screenshot](https://github.com/luisrausseo/luisrausseo.github.io/blob/master/Project_1/p1.Rausseo.jpg)

### Interactions/Animations

#### Nite Nite Box

The sun changes position when the Nite Nite box in clicked. It changes the y-coordinate from 0 to 1.1 in 0.1 steps. 

![Nite Nite box gif]()

```
AFRAME.registerComponent('nite-nite', {
    schema: {
        to: {default: '2.5 2.5 2.5'}
    },

    init: function () {
        this.el.addEventListener('click', function () {
            var sun = document.getElementById('enviro');
            var currentValue = sun.getAttribute("environment", "lightPosition");
            if (currentValue.lightPosition.y < 1) {
                    var y_pos = currentValue.lightPosition.y + 0.1;
                    sun.setAttribute("environment", "lightPosition", "1 " + y_pos + " 0");
            } else {
                sun.setAttribute("environment", "lightPosition", "1 0 0");
            }
        });
    }
});
```

```
<a-entity class="clickable" geometry="height: 1; depth: 1; width: 1" position="-10 1 13" scale="0.5 0.5 0.5" nite-nite=""
          material="color=#f35169">
    <a-animation attribute="rotation"
                from="45 0 45"
                dur="3000"
                to="45 360 45"
                repeat="indefinite"
                easing="linear"></a-animation>
</a-entity>
```

#### Garage Door

The garage door opens/closed when clicked. This is done by changing position and rotation at the same time.

![Garage door gif]()

```
<a-entity id="garage_door" class="clickable" static-body geometry="primitive: box; depth: 0.1; height: 3; width: 4"
          position="2 1.5 7" rotation="0 0 0" material="shader: standard;
          roughness: 1; src: url(images/garage_door.jpg); repeat: 1 2">
    <a-animation begin="click" attribute="position" from="2 1.5 7" to= "2 2.8 7" dur="3000" direction="alternate"></a-animation>
    <a-animation begin="click" attribute="rotation" from="0 0 0" to= "-90 0 0" dur="3000" direction="alternate"></a-animation>
</a-entity>
```

#### Earth

The earth is a giant Collada model which rotates in its own axis by a <a-animation> element. 

![Rotating earth]()

```
<a-entity collada-model="#planet" rotation="45 0 45" position="70 150 -100" scale="80 80 80">
	<a-animation attribute="rotation" from="45 0 45" dur="200000" to="45 360 45" repeat="indefinite" easing="linear"></a-animation>
</a-entity>
```

## Sources

### Models

16 unique models were used in building this project.

* 3 Ball Billiards - https://poly.google.com/view/1DEXg34OJ83
* Wooden Picnic table - https://poly.google.com/view/7-B-Vmz3QtU
* Shower - https://poly.google.com/view/f0zI4v-QAb1
* Simple Door - https://poly.google.com/view/2WB4R5KvYwf
* Open Door - https://poly.google.com/view/eexB7rtcCTT
* Main Door - https://3dwarehouse.sketchup.com/model/a6d5e0da-98f0-4564-bc10-3047e8f2d794/Architect-Series-Contemporary-In-Swing-Hinged-Door-Active-Passive
* Towel - https://poly.google.com/view/3zL-gVL2Pft
* Toilet - https://poly.google.com/view/1Xudt9ErVxm
* Bath Sink - https://poly.google.com/view/2ksg-hSb6Vz
* Solar Panel - https://3dwarehouse.sketchup.com/model/6795370752566aad734a703453e2dabe/Solar-Panel
* Ford Fiesta - https://3dwarehouse.sketchup.com/model/u83dd90d9-eaef-4625-a2cd-c05317282835/Ford-Fiesta-Sport-2008
* Computer Desk - https://3dwarehouse.sketchup.com/model/e5ebc54a85f6878ab610b0c94236463/CGM-PC-desk-1600
* Earth - https://3dwarehouse.sketchup.com/model/84ba0734d1be71ccec0b0222b3b6933e/earth
* Air Conditioning - https://3dwarehouse.sketchup.com/model/4f72673fefe957f86fb9835a6f31829e/Ar-Condicionado-Interno
* Kitchen - https://3dwarehouse.sketchup.com/model/d8ef168d7ebc721d8837b930a67ec3ed/cocina-01
* Sofa - https://3dwarehouse.sketchup.com/model/4b49d25e-0150-49aa-8e93-af2fde687f5e/Le-Corbusiers-LC2-Style-Living-Room-Set-Low-Poly

### Textures

* Wood Floor 1 - http://www.thinkstockphotos.com/image/stock-photo-seamless-wood-floor-texture-hardwood-floor/645858422

* Wood Floor 2 - 

* Kitchen Floor - http://www.damarals.com/21783/floor/best-vinyl-flooring-black-ecostep-black-slate-tile-589-cushioned-vinyl-flooring-factory/

* Black Wood - http://wpliving.net/70-free-seamless-wood-backgrounds-2017/

* Garage Door - http://www.precisiondoorstl.com/doors_wd9600.asp

* Outdoor floor - https://www.sketchuptextureclub.com/textures/architecture/paving-outdoor/concrete/blocks-mixed/concrete-paving-outdoor-texture-seamless-20557

* White Wall - https://www.flickr.com/photos/chaoslotus/3271031590

### Art

* Batman - http://snappypixels.com/wp-content/uploads/2014/01/smithbatman.jpg

* Paris - https://esmehome.files.wordpress.com/2012/09/406685.jpg

