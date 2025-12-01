<details>
  <summary>
    ## Função buscar_usuario_por_id:
  </summary>

  <p>
Busca por um laço de repetição limitado pela quantidade de usuarios na rede, comparado ao parametro **id;**

Retorna o indice encontrado.

```jsx
int buscar_usuario_por_id(const RedeSocial *rede, int id) {
    int i; /* Declaração de variável no início da função */
    for (i = 0; i < rede->num_usuarios; i++) { /* looping para buscar usuarios */
        if (rede->usuarios[i].id == id) {
            return i;
        }
    }
    return -1;
}
```
</p>
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
  </ul>
</details>



## Função buscar_amizade:

Busca por um laço de repetição limitado pela quantidade de amigos dentro de usuario, comparado ao parametro **id;**

Retorna o indice da amizade encontrada.

```jsx
int buscar_amizade(const Usuario *usuario, int id_amigo) {
    int i; /* Declaração de variável no início da função */
    for (i = 0; i < usuario->num_amigos; i++) {
        if (usuario->amigos[i] == id_amigo) {
            return i;
        }
    }
    return -1;
}
```

## Função adicionar_usuario:

Valida se o numero de usuarios já foi ultrapassado comparando a variavel MAX_USUARIO.

Se sim: para o codigo e exibe mensagem de erro; 

Se não: 

    Define o id do usuario a partir do numero de usuarios na lista usuarios em rede +1. 

    Usa strncpy para guardar o nome digitado na variavel nome do usuario. 

    O mesmo para idade.

    Define o num_amigos em 0;
    
    Incrementa a quantidade de usuarios na rede.

    Exibe a informação de criação de usuario.

    Retorna o id do novo usuario..

```jsx
int adicionar_usuario(RedeSocial *rede, const char *nome, int idade) {
    int novo_indice;
    Usuario *novo_usuario;

    if (rede->num_usuarios >= MAX_USUARIOS) {
        printf("ERRO: Limite máximo de usuários atingido.\n");
        return -1;
    }

    novo_indice = rede->num_usuarios;
    novo_usuario = &rede->usuarios[novo_indice];

    novo_usuario->id = proximo_id++;
    strncpy(novo_usuario->nome, nome, MAX_NOME - 1);
    novo_usuario->nome[MAX_NOME - 1] = '\0';
    novo_usuario->idade = idade;
    novo_usuario->num_amigos = 0;

    rede->num_usuarios++;
    printf("Usuário '%s' (ID: %d) adicionado com sucesso.\n", nome, novo_usuario->id);
    return novo_usuario->id;
}
```
