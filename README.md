# wshi0890_TUT2_Quiz_8

**This is my research report**

- [wshi0890\_TUT2\_Quiz\_8](#wshi0890_tut2_quiz_8)
  - [PART 1: Imaging Technique Inspiration](#part-1-imaging-technique-inspiration)
  - [PART 2: Coding Technique Exploration](#part-2-coding-technique-exploration)


## PART 1: Imaging Technique Inspiration
My inspirations come from a Promotional Video for the game ***Zenless Zone Zerod***. The game isn't even official issued yet, but when it's first Promotional Video was posted, I was very attracted by some of the images in it. So I think some of the imaging techniques used in it that I can learn. 

According to the assignment requirements, I would like to use layered geometric patterns in the final project, and this case has the layered appearance. It also used a fading effect so that the overall image looks smooth and does not seem stiff.

Here are some screenshots of the Promotional Video:

![1](readmeImages/1.png)
![2](readmeImages/2.png)
![3](readmeImages/3.png)
![4](readmeImages/4.png)

## PART 2: Coding Technique Exploration
I would like to use the code to make an effect similar to the screenshot above: The image follows the mouse slide panning left and right, at the same time the image or the text of the next layer appears, and the next layer image can produce a fading effect.

I didn't find code that directly implements my idea, but I found several codes that combined have the potential to achieve the effect I described.

1. [Directional](https://p5js.org/examples/lights-directional.html)

![5](readmeImages/5.png)

```
const radius = 200;

function setup() {
  createCanvas(710, 400, WEBGL);
  noStroke();
  fill(200);
}

function draw() {
  noStroke();
  background(0);
  const dirY = (mouseY / height - 0.5) * 4;
  const dirX = (mouseX / width - 0.5) * 4;
  directionalLight(204, 204, 204, dirX, dirY, 1);
  translate(-1.5 * radius, 0, 0);
  sphere(radius);
  translate(3 * radius, 0, 0);
  sphere(radius);
}

```

2. [Alpha Mask](https://p5js.org/examples/image-alpha-mask.html)

![6](readmeImages/6.png)

```
let img;
let imgMask;

function preload() {
  img = loadImage('assets/moonwalk.jpg');
  imgMask = loadImage('assets/mask.png');
}

function setup() {
  createCanvas(720, 400);
  img.mask(imgMask);
  imageMode(CENTER);
}

function draw() {
  background(0, 102, 153);
  image(img, width / 2, height / 2);
  image(img, mouseX, mouseY);
}

```
