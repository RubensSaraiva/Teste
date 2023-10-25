# Imagem feita para a questão aberta do teste
### " Imagine que você é o(a) arquiteto(a) responsável pelo desenho de um sistema de logins para um site extremamente concorrido de ingressos de um mega show de Rock em Rio (got it?). Dado que o número de ingressos é limitado e muito inferior a quantidade de acessos no dia venda, você precisa garantir que o site só irá finalizar a venda para pessoas que realmente vão receber o ingresso, ou seja, você não pode deixar uma pessoa comprar um ingresso sem que haja mais disponíveis. Além disso, um cliente com internet mais lenta não ficaria feliz de não conseguir comprar seu ingresso pois uma pessoa com internet mais veloz passou sua frente."
 #Codigo PrintUML

 @startuml
!theme aws-orange
left to right direction
actor User
package acoesUsuario {
  usecase "Vizualiza Ingressos disponivel na Fila" as uc1
  usecase "Entrar na Fila de espera" as uc2
  usecase "Remove do carinho" as uc3
  usecase "Confirma Pagamento" as uc4
}

package respostasSistemas {
  usecase "Reserva o ingresso se disponivel" as ucS1
  usecase "Devolve o ingreso para a fila" as ucS2
  usecase "Finaliza a compra" as ucS3
  usecase "notificar Usuario com as informacoes " as ucS4

}
User --> uc1
User --> uc2
User --> uc3
User --> uc4
uc2 ..> uc4
uc2 -->ucS1
uc2 ..>uc3
uc3 -->ucS2
uc4 -->ucS3
ucS3 -->ucS4

@enduml
