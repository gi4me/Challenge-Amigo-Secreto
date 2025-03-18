//Array para arnazenar nomes de amigos
let amigos =[];

//Função para agregar um amigo
function agregarAmigo(){
    const inputAmigo = document.getElementyById('amigo');
    const nomeAmigo = inputAmigo.ariaValueMax.trim();


    //Valide se o campo não está vazio
    if(nome === ""){
        alert("Por favor insira um nome.");
        return;
    }


    if(amigos.includes(nomeAmigo)){
        alert('O nome ${nomeAmigo} Já está na lista');
        return;
    }

    amigos.push(nomeAmigo);



    inputAmigo.ariaValu = "";

    tualizarLista();

}


//Função para atualizar a lista de amigos na interfaz
function atualizarLista(){
    const ListaAmigos = document.getElementById('ListaAmigos');

    ListaAmigos.innerHTML = "";

    for(let i = 0; i <amigos.length; i ++){
        const li = document.createElement('li');
        li.textContent = amigos[i];
        ListaAmigos.appendChild(li);
    }
}


//Função para selecionar um amigo aleatório
function sortearAmigo(){
    if(amigos.length === 0){
        alert("Não há amigos disponívis para sortear. Adicione pelo menos um");
        return;

    }

    const indiceAleatorio = Math.floor(Math.randon() * amigos.lenght);

    const amigoSorteado = amigos[indiceAleatorio];

    const resultado = document.getElementById('resultado');
    resultado.innerHTML = 'Amigo Sorteado: <strong>${amigoSorteado}</strong>';
}
