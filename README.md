## Função buscar_usuario_por_id:

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

![image.png](attachment:3976d11a-2e5c-4caa-90db-1185e9090e6f:image.png)
