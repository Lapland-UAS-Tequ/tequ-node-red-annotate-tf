tequ-node-red-annotate-tf
=====================

Annotates prediction results using canvas.

## Install

Run the following command in your Node-RED user directory - typically `~/.node-red`

        npm install tequ-node-red-annotate-tf

## Information

Annotates object detection prediction results.

This node is developed to work with other Tequ nodes.
- Expects image in "msg.payload"
- Expects prediction result in "msg.data.properties.computer_vision.result"
- Expects prediction labels in "msg.data.properties.computer_vision.labels"
- Uses canvas for annotation
- Uses tfjs-node-gpu for thumbnail generation 

Prediction result is expected to be array of objects

```
{
	"bbox":[x,y,w,h],

	"class":"name",

	"label":"name",

	"id":0,

	"score":0.643

}
```

Prediction labels is expected to be array of strings: ["label1","label2"]


Annotation threshold is looked up from:
1. global variable "settings" property "threshold"
2. input "msg" property "threshold"
3. env variable "threshold" in node configuration

Dependencies
- https://www.npmjs.com/package/@tensorflow/tfjs-node-gpu
- https://www.npmjs.com/package/node-canvas

Installation of canvas & tfjs-node-gpu can be tricky in some environments.
