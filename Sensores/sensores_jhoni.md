# Sensores

## Sensor de luminosidade (Mh sensor Series Flying-fish)
![enter image description here](https://www.usinainfo.com.br/1034555-thickbox_default/modulo-sensor-de-luminosidade-ldr-4-pinos-saida-digital-e-analogica.jpg)

## Portas Pin


| PIN|VALOR  |
|--|--|
| A0 |ENTRADA ANALÓGICA  |
| D0 |ENTRADA DIGITAL  |
| VGG |POSITIVO (3.3-5V)  |
| GND |NEGATIVO(GND) |


## Funcionamento

#### Este modelo é um sensor de luminosidade que usa LM393 que é um módulo que

#### compara uma tensão de entrada (que pode ser checada através da porta A0) e uma

#### tensão de referência que é obtida através do potenciômetro presente em cima do

#### mesmo (Caixa azul), com isto ele retorna uma resposta para o D0 definindo como

#### HIGH ou LOW o mesmo.


#### O sensor aumenta sua resistência quando está em um ambiente claro e a diminui no

#### escuro o que faz com que ao analisar a entrada analógica os valores mais próximos do

#### 0 signifiquem claro e os valores mais próximos do 1023 signifique escuro.

#### É possível se a porta digital está recebendo HIGH ou LOW tanto através do comando

#### digitalRead(porta), tanto através do próprio componente que tem um led que quando

#### está em estado LOW acende e quando está em estado HIGH se apaga, facilitando o

#### ajuste do potenciômetro.

### Código Exemplo De Teste

  

	void  setup()  {

	//Inicia serial

	Serial.begin(9600);

	}

	  

	void  loop()  {

	//Pegar o valor analógico referente a iluminação

	int light = analogRead(A0);

	//Retorna se o valor pego esta igual ou acima do limite definido pelo potenciometro

	bool valid = digitalRead(8);

	Serial.println(light);

	//Quanto mais alto mais escuro então escuro é HIGH e claro LOW

	if(valid == HIGH){

	Serial.println("Escuro");

	}else{

	Serial.println("Claro");

	}

	delay(3000);

	}

## Sensor infra-Vermelho TCRT 5000
![enter image description here](https://www.saravati.com.br/media/catalog/product/cache/ff61517d26ace703648229d56c081b52/9/d/9dcb3c4ac3.jpg)

### Portas Pin


| PIN|VALOR  |
|--|--|
| A0 |ENTRADA ANALÓGICA  |
| D0 |ENTRADA DIGITAL  |
| VGG |POSITIVO (3.3-5V)  |
| GND |NEGATIVO(GND) |


### Funcionamento

#### Este modelo é um sensor infravermelho que funciona da seguinte maneira, o led azul

#### irá mandar um feixe de luz que ao atingir uma superfície deve retornar ao led preto em

#### caso de isto acontecer a porta digital retorna HIGH senão deverá retornar LOW.

#### A sensibilidade do feixe pode ser ajustada através do potenciômetro acima do mesmo

#### para que ele detecte mais facilmente superfícies não reflexivas e vice-versa.

### Código Exemplo De Teste


  

	void  setup()  {

	Serial.begin(9600);

	}

	  

	void  loop()  {

	//Pega o valor de reflexão caso algo seja refletido o valor sera alto

	int reflection = analogRead(A0);

	//checa se o valor da reflexão esta de acordo com o potenciometro

	bool valid = digitalRead(8);

	Serial.println(reflection);

	//Caso a reflexão seja HIGH ele achou uma superficie desejada do contrario sera LOW

	if(valid == HIGH){

	Serial.println("ACHOU");

	}else{

	Serial.println("FALHOU");

	}

	delay(3000);

	}

