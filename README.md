# Simulador-Trajet-ria-Bola-de-Futebol-Falta
Simulador da Trajetória de uma bola de Futebol em uma Falta

É recomendável rodar o código em "glowscript.org". Versão Web VPython 3.2

_________________________________________________________________________________________________________________________________________

Web VPython 3.2

# POSIÇÕES

#x = cylinder(pos=vector(0,50,0), size=vector(20,1,1), color=color.blue)
#y = cylinder(pos=vector(0,50,0), size=vector(1,20,2), color=color.red) 
#z = cylinder(pos=vector(0,50,0), size=vector(1,1,20), color=color.yellow) 


# TRABALHO SIMULAÇÃO DA TRAJETÓRIA DE UMA BOLA DE FUTEBOL EM UMA FALTA

scene.title="Simulação da Trajetória de uma Bola de Futebol em uma Falta"
scene.width = 1200
scene.height = 500
#scene.width=scene.height=800

##### Botão de iniciar
    
INICIAR = False
def acionar_btn():
    global INICIAR
    INICIAR = True

button(text="INICIAR", bind=acionar_btn)

##### CAMPO DE FUTEBOL:

# GOLEIRO E BARREIRA (OPCIONAIS)

goleiro = box(pos=vector(60,1.5,0), size=vector(0.3,3.0,1.0), color=color.yellow)
bar = box(pos=vector(33.8,1.5,5), size=vector(0.3,3.0,2.0), color=color.red)     # Barreira

# LADO DIREITO                   

campo = box(pos=vector(0,0,0), size=vector(120,0.001,90), color=color.green)

linha1 = cylinder(pos=vector(0,0,0), size=vector(0.3,0.3,90), color=color.white)
meio = box(pos=vector(0,0,0), size=vector(2,0.3,2), color=color.white)

fora1 = cylinder(pos=vector(-60,0,45), size=vector(120,0.3,0.3), color=color.white)
fora2 = cylinder(pos=vector(-60,0,-45), size=vector(120,0.3,0.3), color=color.white)
fora3 = cylinder(pos=vector(60,0,0), size=vector(0.3,0.3,90), color=color.white)
fora4 = cylinder(pos=vector(-60,0,0), size=vector(0.3,0.3,90), color=color.white)

trave1 = box(pos=vector(60,0,7.32), size=vector(0.3,10,0.3), color=color.white)
trave2 = box(pos=vector(60,0,-7.32), size=vector(0.3,10,0.3), color=color.white)
travessao = box(pos=vector(60,5,0), size=vector(0.3,0.3,14.942), color=color.white)

linha_gol1 = box(pos=vector(57.25,0,12.82), size=vector(5.5,0.3,0.3), color=color.white)
linha_gol2 = box(pos=vector(57.25,0,-12.82), size=vector(5.5,0.3,0.3), color=color.white)
linha_gol3 = box(pos=vector(54.5,0,0), size=vector(0.3,0.3,26.1), color=color.white)

linha_superior1 = box(pos=vector(51.75,0,20.16), size=vector(16.5,0.3,0.3), color=color.white)
linha_superior2 = box(pos=vector(51.75,0,-20.16), size=vector(16.5,0.3,0.3), color=color.white)
linha_superior2 = box(pos=vector(43.5,0,0), size=vector(0.3,0.3,40.32), color=color.white)

penalti = box(pos=vector(43.5,0,0), size=vector(1.0,0.3,1.0), color=color.white)

# LADO ESQUERDO

trave1e = box(pos=vector(-60,0,7.32), size=vector(0.3,10,0.3), color=color.white)
trave2e = box(pos=vector(-60,0,-7.32), size=vector(0.3,10,0.3), color=color.white)
travessaoe = box(pos=vector(-60,5,0), size=vector(0.3,0.3,14.942), color=color.white)

linha_gol1e = box(pos=vector(-57.25,0,12.82), size=vector(5.5,0.3,0.3), color=color.white)
linha_gol2e = box(pos=vector(-57.25,0,-12.82), size=vector(5.5,0.3,0.3), color=color.white)
linha_gol3 = box(pos=vector(-54.5,0,0), size=vector(0.3,0.3,26.1), color=color.white)

linha_superior1e = box(pos=vector(-51.75,0,20.16), size=vector(16.5,0.3,0.3), color=color.white)
linha_superior2e = box(pos=vector(-51.75,0,-20.16), size=vector(16.5,0.3,0.3), color=color.white)
linha_superior2e = box(pos=vector(-43.5,0,0), size=vector(0.3,0.3,40.32), color=color.white)

penaltie = box(pos=vector(-43.5,0,0), size=vector(1.0,0.3,1.0), color=color.white)

# GOL (LADO DIREITO)

sustentacao1 = box(pos=vector(65,0,7.32), size=vector(10,0.3,0.3), color=color.white)
sustentacao2 = box(pos=vector(65,0,-7.32), size=vector(10,0.3,0.3), color=color.white)
sustentacao3 = box(pos=vector(70,0,0), size=vector(0.3,0.3,14.64), color=color.white)
sustentacao4_cima_primeiro = box(pos=vector(63,5,0), size=vector(0.3,0.3,14.942), color=color.white)
sustentacao5_cima_meio = box(pos=vector(66,3,0), size=vector(0.3,0.3,14.942), color=color.white)
sustentacao6_cima_terceiro = box(pos=vector(69,1,0), size=vector(0.3,0.3,14.942), color=color.white)

grama = box(pos=vector(65,0,0), size=vector(30,0.001,60), color=color.green)

# Linhas horizontais do gol

barra1d = box(pos=vector(61.5,5,7.32), size=vector(3,0.3,0.3), color=color.white)     
barra2d = box(pos=vector(64.5,3,7.32), size=vector(3,0.3,0.3), color=color.white)
barra3d = box(pos=vector(67.5,1,7.32), size=vector(3,0.3,0.3), color=color.white)

barra1e = box(pos=vector(61.5,5,-7.32), size=vector(3,0.3,0.3), color=color.white)
barra2e = box(pos=vector(64.5,3,-7.32), size=vector(3,0.3,0.3), color=color.white)
barra3e = box(pos=vector(67.5,1,-7.32), size=vector(3,0.3,0.3), color=color.white)

# Linhas verticais do gol

coluna1d = box(pos=vector(63,2.5,7.32), size=vector(0.3,5,0.3), color=color.white)
coluna2d = box(pos=vector(66,1.5,7.32), size=vector(0.3,3,0.3), color=color.white)
coluna3d = box(pos=vector(69,0.5,7.32), size=vector(0.3,1,0.3), color=color.white)

coluna2e = box(pos=vector(63,2.5,-7.32), size=vector(0.3,5,0.3), color=color.white)
coluna2e = box(pos=vector(66,1.5,-7.32), size=vector(0.3,3,0.3), color=color.white)
coluna3e = box(pos=vector(69,0.5,-7.32), size=vector(0.3,1,0.3), color=color.white)

# Rede

tampa1 = box(pos=vector(61.5,5,0), size=vector(3,0.3,7.32*2), color=color.white)
tampa2 = box(pos=vector(64.5,3,0), size=vector(3,0.3,7.32*2), color=color.white)
tampa3 = box(pos=vector(67.5,1,0), size=vector(3,0.3,7.32*2), color=color.white)

cobertura1 = box(pos=vector(63,4,0), size=vector(0.3,2,7.32*2), color=color.white)
cobertura2 = box(pos=vector(66,2,0), size=vector(0.3,2,7.32*2), color=color.white)
cobertura3 = box(pos=vector(69,0,0), size=vector(0.3,2,7.32*2), color=color.white)

rede_direita_1 = box(pos=vector(61.5,2.5,7.32), size=vector(3,5,0.3), color=color.white)
rede_direita_2 = box(pos=vector(64.5,1.5,7.32), size=vector(3,3,0.3), color=color.white)
rede_direita_3 = box(pos=vector(67.5,0.5,7.32), size=vector(3,1,0.3), color=color.white)

rede_esquerda_1 = box(pos=vector(61.5,2.5,-7.32), size=vector(3,5,0.3), color=color.white)
rede_esquerda_2 = box(pos=vector(64.5,1.5,-7.32), size=vector(3,3,0.3), color=color.white)
rede_esquerda_3 = box(pos=vector(67.5,0.5,-7.32), size=vector(3,1,0.3), color=color.white)

rede_final = box(pos=vector(69,0.5,0), size=vector(0.3,1,14.942), color=color.white)


##### BOLA

raio = 0.11   
bola = sphere(radius=raio, color=color.cyan)

def xShift(s):     # Coloca o "controle deslizante x" ao rodar o programa
    bola.pos.x = s.value
    xs_caption.text = 'x = '+'{:1.2f}'.format(xs.value)+"\n\n"
xs = slider(bind=xShift,min=-60,max=60,value=25.32)
xs_caption = wtext(text='x = '+'{:1.2f}'.format(xs.value)+"\n\n")

def yShift(s):     # Coloca o "controle deslizante y" ao rodar o programa
    bola.pos.y = s.value
    ys_caption.text = 'y = '+'{:1.2f}'.format(ys.value)+"\n\n"
ys = slider(bind=yShift,min=0,max=raio,value=raio)
ys_caption = wtext(text='y = '+'{:1.2f}'.format(ys.value)+"\n\n")

def zShift(s):     # Coloca o "controle deslizante z" ao rodar o programa
    bola.pos.z = s.value
    zs_caption.text = 'z = '+'{:1.2f}'.format(zs.value)+"\n\n"
zs = slider(bind=zShift,min=-45,max=45,value=4.98)
zs_caption = wtext(text='z = '+'{:1.2f}'.format(zs.value)+"\n\n")

A = pi*(raio)**2     # Área da Bola
V = (4/3)*pi*raio**3     # Volume da Bola

##### VELOCIDADE INICIAL DA BOLA

b = float(input("Digite um ângulo em graus (entre 0 e 90) = "))
theta = pi*(b/180)     # Ângulo - passa de graus para radianos

p = float(input("Velocidade x = "))
m = float(input("Velocidade y = "))
n = float(input("Velocidade z = "))
bola.v = vector(p*cos(theta), m*sin(theta), n)      # Velocidade inicial da bola

##### DADOS

g = vector(0, -9.8, 0)
M = 0.454
f = float(input("Digite o número de giros/segundo da bola:"))

##### DADOS FORÇA DE ARRASTO

denar = 1.224     # Densidade do ar ao nível do MAR
n = 0.000018     # Viscosidade do ar

##### MOMENTO LINEAR DA BOLA

bolap = M*bola.v

##### TEMPO

deltat = 0.02     # 0.1
t = 0
tfinal = 6

##### ATUALIZANDO POSIÇÕES

while t < tfinal:
    rate(50)
    if INICIAR:
        attach_trail(bola)     # Marca a trajetória da bola
        velocidade = bolap/M

        if bola.pos.y < campo.pos.y:    
            bolap.y = (-1)*bolap.y     # Bola é refletida ao se chocar com o chão
    
        Re = (denar*2*raio*mag(bola.v))/n     # Número de Reynolds
        
        if Re <= 300000:
            Ca = 0.5     # Para 10e3 < Re < 3*10e5  
        elif Re > 300000:
            Ca = 0.01     # Aumento da velocidade
            
        Cm = 1.0     # Coeficiente de Magnus
         
        w = vector(0,2*pi*f,0)
        
        p_vet = cross(w, bola.v)
        
        Faras = (((1/2)*(denar)*(A)*(Ca)*mag(bola.v)))*norm(bola.v)
        Fg = M*g
        Fmag = (((1/2)*(denar)*(A)*(Cm)*(raio)))*(((p_vet)))
        E = denar*(-g)*V
        
        Fres = Fg - Faras + Fmag + E
        
        ##################################################################################################
        
        ### COLISÕES
        
        # COLISÃO TRAVE 1 - trave1 = box(pos=vector(60,0,7.32), size=vector(0.3,10,0.3), color=color.white)
        if 59.7 <= bola.pos.x <= 60.2 and 0 <= bola.pos.y <= 5.2 and 7 <= bola.pos.z <= 7.5:
            bolap.x = (-1)*bolap.x
            t = tfinal/1.5     # Apenas para acabar mais rápido
        
        # COLISÃO TRAVE 2 - trave2 = box(pos=vector(60,0,-7.32), size=vector(0.3,10,0.3), color=color.white)
        if 59.7 <= bola.pos.x <= 60.2 and 0 <= bola.pos.y <= 5.2 and -7.5 <= bola.pos.z <= -7:
            bolap.x = (-1)*bolap.x
            t = tfinal/1.5
        
        # COLISÃO TRAVESSÃO - travessao = box(pos=vector(60,5,0), size=vector(0.3,0.3,15.1), color=color.white)
        if 59.8 <= bola.pos.x <= 60.1 and 4.9 <= bola.pos.y <= 5.1 and -7.1 <= bola.pos.z <= 7.1:     # y: 7,32 (tamanho travessão) + 0,15
            bolap.x = (-1)*bolap.x
            t = tfinal/1.5
        
        # COLISÃO GOLEIRO - goleiro = box(pos=vector(60,1.5,0), size=vector(0.3,3.0,1.0), color=color.yellow)
        if 59.7 <= bola.pos.x <= 60.1 and 0 <= bola.pos.y <= 3.1 and -0.6 <= bola.pos.z <= 0.6:
            bolap.x = (-1)*bolap.x
            t = tfinal/1.5
        
        # COLISÃO BARREIRA - box(pos=vector(33.8,1.5,5), size=vector(0.3,3.0,2.0), color=color.red)
        if (bar.pos.x-0.5 <= bola.pos.x <= bar.pos.x+0.5) and (0 <= bola.pos.y <= (bar.size.y)+0.2) and ((-bar.size.z/2)+0.2+bar.pos.z <= bola.pos.z <= (bar.size.z/2)+0.2+bar.pos.z):
            bolap.x = (-1)*bolap.x
            t = tfinal/1.5

        
        
        # COLISÃO - tampa1 = box(pos=vector(61.5,5,0), size=vector(3,0.3,7.32*2), color=color.white)
        if 60.1 <= bola.pos.x <= 64.6 and 4.7 <= bola.pos.y <= 5.1 and -7.22 <= bola.pos.z <= 7.42:
            bolap.y = (-1)*bolap.y     # No caso, pode-se escolher entre a bola refletir ao colidir, ou o programa se encerrar ao colidir
            t = tfinal     # Se a bolar encontrar o gol, o programa se encerra  
        
        # COLISÃO - tampa2 = box(pos=vector(64.5,3,0), size=vector(3,0.3,7.32*2), color=color.white)
        if 63.4 <= bola.pos.x <= 66.6 and 2.7 <= bola.pos.y <= 3.1 and -7.22 <= bola.pos.z <= 7.42:
            bolap.y = (-1)*bolap.y
            t = tfinal
        
        # COLISÃO - tampa3 = box(pos=vector(67.5,1,0), size=vector(3,0.3,7.32*2), color=color.white)
        if 66.4 <= bola.pos.x <= 69.6 and 0.7 <= bola.pos.y <= 1.1 and -7.22 <= bola.pos.z <= 7.42:
            bolap.y = (-1)*bolap.y
            t = tfinal

        # COLISÃO - cobertura1 = box(pos=vector(63,4,0), size=vector(0.3,2,7.32*2), color=color.white)
        if 62.7 <= bola.pos.x <= 63.2 and 2.9 <= bola.pos.y <= 5.1 and -7.22 <= bola.pos.z <= 7.42:
            bolap.x = (-1)*bolap.x
            t = tfinal
        
        # COLISÃO - #cobertura2 = box(pos=vector(66,2,0), size=vector(0.3,2,7.32*2), color=color.white)
        if 65.7 <= bola.pos.x <= 66.2 and 0.9 <= bola.pos.y <= 3.1 and -7.22 <= bola.pos.z <= 7.42:
            bolap.x = (-1)*bolap.x
            t = tfinal
        
        # COLISÃO - #cobertura3 = box(pos=vector(69,0,0), size=vector(0.3,2,7.32*2), color=color.white)
        if 68.7 <= bola.pos.x <= 69.2 and 0 <= bola.pos.y <= 1.1 and -7.22 <= bola.pos.z <= 7.42:
            bolap.x = (-1)*bolap.x
            t = tfinal
        
        # COLISÃO - rede_direita_1 = box(pos=vector(61.5,2.5,7.32), size=vector(3,5,0.3), color=color.white)
        if 60.3 <= bola.pos.x <= 63.2 and 0 <= bola.pos.y <= 5.2 and 7.02 <= bola.pos.z <= 7.62:
            bolap.z = (-1)*bolap.z
            t = tfinal
        
        
        # COLISÃO - rede_direita_2 = box(pos=vector(64.5,1.5,7.32), size=vector(3,3,0.3), color=color.white)
        if 62.7 <= bola.pos.x <= 66.2 and 0 <= bola.pos.y <= 5.2 and 7.12 <= bola.pos.z <= 7.52:
            bolap.z = (-1)*bolap.z
            t = tfinal
        
        
        # COLISÃO - rede_direita_3 = box(pos=vector(67.5,0.5,7.32), size=vector(3,1,0.3), color=color.white)
        if 65.7 <= bola.pos.x <= 69.2 and 0 <= bola.pos.y <= 5.2 and 7.12 <= bola.pos.z <= 7.52:
            bolap.z = (-1)*bolap.z
            t = tfinal
        
        # COLISÃO - rede_esquerda_1 = box(pos=vector(61.5,2.5,7.32), size=vector(3,5,0.3), color=color.white)
        if 60.3 <= bola.pos.x <= 63.2 and 0 <= bola.pos.y <= 5.2 and -7.62 <= bola.pos.z <= -7.02:
            bolap.z = (-1)*bolap.z
            t = tfinal
        
        
        # COLISÃO - rede_esquerda_2 = box(pos=vector(64.5,1.5,7.32), size=vector(3,3,0.3), color=color.white)
        if 62.7 <= bola.pos.x <= 66.2 and 0 <= bola.pos.y <= 5.2 and -7.52 <= bola.pos.z <= -7.12:
            bolap.z = (-1)*bolap.z
            t = tfinal
        
        
        # COLISÃO - rede_esquerda = box(pos=vector(67.5,0.5,7.32), size=vector(3,1,0.3), color=color.white)
        if 65.8 <= bola.pos.x <= 69.2 and 0 <= bola.pos.y <= 5.2 and -7.52 <= bola.pos.z <= -7.12:
            bolap.z = (-1)*bolap.z
            t = tfinal

        ### ATUALIZANDO A POSIÇÃO DA BOLA
        
        bolap = bolap + (Fres)*deltat
        
        bola.pos = bola.pos + (bolap/M)*deltat
        
        bola.v = bolap/M

        scene.camera.follow(bola)
        bola.rotate(angle=pi/2, axis=w)

        t += deltat
