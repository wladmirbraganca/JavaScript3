# Jantar_dos_filosofos

## Explicação da Solução com Garçom

### 1. Variável MAX_FILOSOFOS_COMENDO:

O garçom permite até n-1 filósofos comerem ao mesmo tempo, onde n é o número total de filósofos. Isso garante que nunca haverá uma situação em que todos os filósofos pegam um garfo ao mesmo tempo, evitando deadlock.

### 2. Variável filosofosComendo:

Mantém o controle de quantos filósofos estão comendo simultaneamente. Se o número de filósofos comendo atingir o limite (MAX_FILOSOFOS_COMENDO), os outros filósofos precisam esperar.

### 3. Garçom (garcomDisponivel):

Embora seja uma variável simples, ela controla quando o garçom está disponível para permitir que os filósofos comam.

### 4. Espera Assíncrona:

Caso um filósofo não consiga comer devido ao limite de filósofos comendo, ele espera de forma assíncrona (esperarAleatorio) antes de tentar novamente.

### 5. Estado esperando:

Enquanto o filósofo aguarda a permissão do garçom para pegar os garfos, ele entra no estado esperando, o que previne que ele bloqueie outros filósofos.


**Evita Deadlock:** Com essa abordagem, o deadlock é evitado porque o garçom garante que não mais que n-1 filósofos possam pegar os garfos ao mesmo tempo.

**Minimiza Starvation:** A starvation é minimizada porque, eventualmente, cada filósofo terá a chance de pegar os garfos assim que outros terminarem de comer.
