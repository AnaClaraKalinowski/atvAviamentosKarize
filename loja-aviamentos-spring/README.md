# loja-aviamentos-spring
Etapa 1 — Usuário & Login do projeto Loja de Aviamentos e Tintas, usando Spring Boot + Spring Security 6 + JPA + H2 + Thymeleaf + Bootstrap. Esta etapa já com cadastro, autenticação e telas básicas.
1) Requisitos
**Requisitos Funcionais (RF)**
1.	RF01 — Cadastrar usuário (nome, e-mail único, senha com hash, perfil).
2.	RF02 — Autenticar usuário via e-mail + senha.
3.	RF03 — Manter sessão autenticada e exibir nome do usuário logado.
4.	RF04 — Logout seguro (invalidar sessão).
5.	RF05 — Acesso à /home apenas autenticado.
6.	RF06 — E-mail deve ser único no sistema.
7.	RF07 — Exibir feedbacks de erro (login inválido, e-mail já existente, validações).
8.	RF08 — Habilitar /h2-console apenas em dev.
   
**Requisitos Não Funcionais (RNF)**
1.	RNF01 — Segurança: senhas com BCrypt; proteção CSRF habilitada (formulários Thymeleaf).
2.	RNF02 — Persistência em H2 (dev), JPA/Hibernate.
3.	RNF03 — UI responsiva com Bootstrap 5 + Thymeleaf.
4.	RNF04 — Código organizado em camadas: controller, service, repository, domain.
5.	RNF05 — Validação com Bean Validation (javax/jakarta).
6.	RNF06 — Padrão de logs de autenticação (sucesso/falha).
7.	RNF07 — Preparado para trocar H2 por outro SGBD depois (configuração externa).
________________________________________
**2) Casos de Uso (texto)**

***UC-01: Registrar Usuário***

**Ator:** Visitante

**Fluxo:** abre “Criar conta” → informa nome, e-mail, senha, confirma → sistema valida, cria usuário com senha hash e perfil ROLE_USER → redireciona para login com mensagem de sucesso.

**Exceções: **e-mail em uso; senha fraca; campos obrigatórios.

***UC-02: Autenticar Usuário***

**Ator:** Usuário

**Fluxo:** abre “Login” → informa e-mail/senha → sistema autentica via Spring Security → redireciona para /home.

**Exceções:** credenciais inválidas (mensagem amigável).
