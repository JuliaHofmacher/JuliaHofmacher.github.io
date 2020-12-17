<html>
    <head>
        <script src="https://aframe.io/releases/1.1.0/aframe.min.js"></script>
    </head>
    <body>
        <a-scene>
            <a-assests>
                <img id="sky" src="assets/space.jpg">
                <img id="ground" src="assets/space.jpg">
                <img id="earth" src="assets/earth.jpg">
                <img id="moon" src="assets/moon.jpg">
                <a-asset-item id="alien" src="assets/alien/scene.gltf"></a-asset-item>
                <audio id="sound" src="assets/sound.mp3"></audio>
            </a-assests>

            
            <a-plane src="#ground" height="100" width="100" rotation="-90 0 0 "></a-plane>
            <a-sky src="#sky"></a-sky>
            <a-camera>
                <a-cursor color="white" position="0 0 -1"></a-cursor> 
            </a-camera>
            <a-entity id="mouseCursor" cursor="rayOrigin: mouse"></a-entity>

            <a-entity
                position="0 3 -6"
                geometry="primitive: circle"
                material="src:assets/earth.jpg"
                animation__mouseenter="property: components.material.material.color; type: color; to: purple; startEvents: mouseenter; dur: 500";
                animation__mouseleave="property: components.material.material.color; type: color; to: #d1e2ff; startEvents: mouseleave; dur: 500";
                src="assets/earth.jpg"
            ></a-entity>

            <a-entity 
                rotation="0 0 0" 
                material="src:assets/moon.jpg" 
                src="assets/moon.jpg; assetes/sound.mp3" 
                animation="property: rotation; to: 0 360 0; loop: true; dur: 10000">
                <a-sphere 
                    position="3 3 -8" 
                        src="assets/moon.jpg"  
                        sound="src: #sound;loop: true; autoplay: true; distanceModel: exponential; rolloffFactor: 1.5;"
                ></a-sphere>
            </a-entity>

            <a-gltf-model position="1 0 -4" scale="0.2 0.2 0.2" src="#alien"></a-gltf-model>

            <a-box audiohandler></a-box>

            <a-entity light="type: ambient; color: #a4fcf4f"></a-entity>
            <a-entity light="type: point; color: red; intensity: 1.0" position="-1 1 0"></a-entity>
            
        </a-scene>
    </body>
</html>