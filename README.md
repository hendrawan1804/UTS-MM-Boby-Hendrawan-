function setup() {
  createCanvas(600, 400);
}

function draw() {
  background(135, 206, 250); // Latar belakang langit biru muda
  
  drawSun();
  drawMountains();
  drawGround();
  drawRoad();
  drawBirds();
}

function drawSun() {
  fill(255, 223, 0); // Warna matahari kuning
  noStroke();
  ellipse(350, 210, 80, 80); // Matahari di sudut kanan atas

}

function drawMountains() {
  fill(100, 100, 150); // Warna gunung abu-abu kebiruan
  noStroke();
  
  // Gunung kiri
  triangle(100, 300, 250, 120, 400, 300);
  
  // Gunung kanan
  triangle(300, 300, 450, 150, 600, 300);
  
}

function drawGround() {
  fill(34, 139, 34); // Warna tanah hijau
  rect(0, 300, width, 100); // Tanah di bagian bawah
}

function drawRoad() {
  fill(100, 100, 100); // Warna jalan abu-abu gelap
  beginShape();
  vertex(width / 2 - 40, height);
  vertex(width / 2 + 40, height);
  vertex(width / 2 + 10, 300);
  vertex(width / 2 - 10, 300);
  endShape(CLOSE);
  
  // Garis tengah jalan
  stroke(255);
  strokeWeight(2);
  for (let i = 320; i < height; i += 20) {
    line(width / 2, i, width / 2, i + 10);
  }
  noStroke();
}

function drawBirds() {
  stroke(0);
  strokeWeight(2);
  noFill();
  
  // Gambar beberapa burung dengan bentuk "V" sederhana di langit
  for (let i = 0; i < 5; i++) {
    let x = random(50, width - 50);
    let y = random(50, 150);
    line(x, y, x + 10, y - 10);
    line(x + 10, y - 10, x + 20, y);
  }
}
