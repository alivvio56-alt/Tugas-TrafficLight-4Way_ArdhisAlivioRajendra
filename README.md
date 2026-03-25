int merah[]  = {2,5,8,11};
int kuning[] = {3,6,9,12};
int hijau[]  = {4,7,10,13};

void setup() {
  for(int i=0;i<4;i++){
    pinMode(merah[i], OUTPUT);
    pinMode(kuning[i], OUTPUT);
    pinMode(hijau[i], OUTPUT);
  }
}

void semuaMerah(){
  for(int i=0;i<4;i++){
    digitalWrite(merah[i], HIGH);
    digitalWrite(kuning[i], LOW);
    digitalWrite(hijau[i], LOW);
  }
}

void kuningKedip(int pin){
  for(int i=0;i<3;i++){
    digitalWrite(pin, HIGH);
    delay(300);
    digitalWrite(pin, LOW);
    delay(300);
  }
}

void aktifkanSimpang(int sisi){
  semuaMerah();

  digitalWrite(merah[sisi], LOW);
  digitalWrite(hijau[sisi], HIGH);

  delay(5000);

  digitalWrite(hijau[sisi], LOW);
  kuningKedip(kuning[sisi]);

  digitalWrite(merah[sisi], HIGH);
}

void loop() {
  aktifkanSimpang(0); // Utara
  delay(2000);

  aktifkanSimpang(1); // Timur
  delay(2000);

  aktifkanSimpang(2); // Selatan
  delay(2000);

  aktifkanSimpang(3); // Barat
  delay(2000);
}
