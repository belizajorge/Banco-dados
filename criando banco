CREATE DATABASE monitoramento;

USE monitoramento;

-- Tabela: Candidatos
CREATE TABLE Candidatos (
    CandidatoID INT PRIMARY KEY AUTO_INCREMENT,
    Nome VARCHAR(50),
    Sobrenome VARCHAR(50),
    Email VARCHAR(100) UNIQUE,
    Telefone VARCHAR(20),
    DataCriacao TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Tabela: Empresas
CREATE TABLE Empresas (
    EmpresaID INT PRIMARY KEY AUTO_INCREMENT,
    Nome VARCHAR(100) NOT NULL,
    Website VARCHAR(100),
    Setor VARCHAR(100),
    Observacoes TEXT,
    DataCriacao TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Tabela: Vagas
CREATE TABLE Vagas (
    VagaID INT PRIMARY KEY AUTO_INCREMENT,
    Titulo VARCHAR(100),
    Localizacao VARCHAR(100),
    Descricao TEXT,
    DataPublicacao DATE,
    EmpresaID INT,
    FOREIGN KEY (EmpresaID) REFERENCES Empresas(EmpresaID)
);

-- Tabela: Statuses
CREATE TABLE Statuses (
    StatusID INT PRIMARY KEY AUTO_INCREMENT,
    NomeStatus VARCHAR(50) NOT NULL UNIQUE
);

-- Tabela: Aplicacoes
CREATE TABLE Aplicacoes (
    AplicacaoID INT PRIMARY KEY AUTO_INCREMENT,
    CandidatoID INT,
    VagaID INT,
    StatusID INT,
    DataAplicacao DATE,
    CurriculoUsado VARCHAR(255),
    CartaApresentacao VARCHAR(255),
    Observacoes TEXT,
    FOREIGN KEY (CandidatoID) REFERENCES Candidatos(CandidatoID),
    FOREIGN KEY (VagaID) REFERENCES Vagas(VagaID),
    FOREIGN KEY (StatusID) REFERENCES Statuses(StatusID)
);

-- Tabela: Contatos
CREATE TABLE Contatos (
    ContatoID INT PRIMARY KEY AUTO_INCREMENT,
    EmpresaID INT,
    Nome VARCHAR(100),
    Email VARCHAR(100),
    Telefone VARCHAR(20),
    Cargo VARCHAR(100),
    Observacoes TEXT,
    FOREIGN KEY (EmpresaID) REFERENCES Empresas(EmpresaID)
);

-- Tabela: Acompanhamentos
CREATE TABLE Acompanhamentos (
    AcompanhamentoID INT PRIMARY KEY AUTO_INCREMENT,
    AplicacaoID INT,
    DataAcompanhamento DATE,
    TipoAcao VARCHAR(100), -- Ex.: E-mail, Ligação, Reunião
    Observacoes TEXT,
    Concluido BOOLEAN DEFAULT FALSE,
    FOREIGN KEY (AplicacaoID) REFERENCES Aplicacoes(AplicacaoID)
);

-- Inserindo na tabela Candidatos
INSERT INTO Candidatos (Nome, Sobrenome, Email, Telefone) VALUES ('João', 'Silva', 'joaosilva@email.com', '(11) 98765-4321'),
INSERT INTO Candidatos (Nome, Sobrenome, Email, Telefone) VALUES ('Maria', 'Oliveira', 'mariaoliveira@email.com', '(21) 99876-5432'),
INSERT INTO Candidatos (Nome, Sobrenome, Email, Telefone) VALUES ('Carlos', 'Mendes', 'carlosmendes@email.com', '(31) 99654-3210'),
INSERT INTO Candidatos (Nome, Sobrenome, Email, Telefone) VALUES ('Ana', 'Lima', 'analima@email.com', '(41) 98523-6547'),
INSERT INTO Candidatos (Nome, Sobrenome, Email, Telefone) VALUES ('Luciano', 'Ferreira', 'lucianoferreira@email.com', '(51) 99874-1234');

-- Inserindo na tabela Empresas
INSERT INTO Empresas (Nome, Website, Setor, Observacoes) VALUES ('Tech Solutions', 'https://techsolutions.com.br ', 'Tecnologia', 'Especializada em desenvolvimento web.'),
INSERT INTO Empresas (Nome, Website, Setor, Observacoes) VALUES ('Green Foods', 'https://greenfoods.com.br ', 'Alimentício', 'Vende produtos naturais e orgânicos.'),
INSERT INTO Empresas (Nome, Website, Setor, Observacoes) VALUES ('Inova RH', 'https://inovarh.com.br ', 'Recursos Humanos', 'Consultoria em recrutamento.'),
INSERT INTO Empresas (Nome, Website, Setor, Observacoes) VALUES ('Blue Engenharia', 'https://blueengenharia.com.br ', 'Engenharia', 'Atua em projetos civis.'),
INSERT INTO Empresas (Nome, Website, Setor, Observacoes) VALUES ('Cloud Services', 'https://cloudservices.com.br ', 'Tecnologia', 'Foco em soluções em nuvem.');

-- Inserindo na tabela Vagas
INSERT INTO Vagas (Titulo, Localizacao, Descricao, DataPublicacao, EmpresaID) VALUES ('Desenvolvedor Frontend', 'São Paulo', 'Criar interfaces responsivas usando React.', '2024-05-10', 1),
INSERT INTO Vagas (Titulo, Localizacao, Descricao, DataPublicacao, EmpresaID) VALUES ('Analista de Marketing', 'Rio de Janeiro', 'Planejar campanhas digitais.', '2024-05-12', 2),
INSERT INTO Vagas (Titulo, Localizacao, Descricao, DataPublicacao, EmpresaID) VALUES ('Assistente de RH', 'Belo Horizonte', 'Apoio no processo seletivo.', '2024-05-11', 3),
INSERT INTO Vagas (Titulo, Localizacao, Descricao, DataPublicacao, EmpresaID) VALUES ('Engenheiro Civil', 'Porto Alegre', 'Supervisionar obras públicas.', '2024-05-13', 4),
INSERT INTO Vagas (Titulo, Localizacao, Descricao, DataPublicacao, EmpresaID) VALUES ('Arquiteto de Soluções em Nuvem', 'Brasília', 'Projetar arquiteturas escaláveis.', '2024-05-14', 5);

-- Inserindo na tabela Statuses
INSERT INTO Statuses (NomeStatus) VALUES ('Pendente'),
INSERT INTO Statuses (NomeStatus) VALUES ('Em análise'),
INSERT INTO Statuses (NomeStatus) VALUES ('Entrevista'),
INSERT INTO Statuses (NomeStatus) VALUES ('Aprovado'),
INSERT INTO Statuses (NomeStatus) VALUES ('Rejeitado');

-- Inserindo na tabela Aplicacoes
INSERT INTO Aplicacoes (CandidatoID, VagaID, StatusID, DataAplicacao, CurriculoUsado, CartaApresentacao, Observacoes) VALUES (1, 1, 2, '2024-05-11', '/curriculos/joao_silva.pdf', '/cartas/joao_frontend.pdf', 'Currículo enviado por e-mail.'),
INSERT INTO Aplicacoes (CandidatoID, VagaID, StatusID, DataAplicacao, CurriculoUsado, CartaApresentacao, Observacoes) VALUES (2, 2, 1, '2024-05-13', '/curriculos/maria_oliveira.pdf', '/cartas/maria_marketing.pdf', 'Candidatura pelo site.'),
INSERT INTO Aplicacoes (CandidatoID, VagaID, StatusID, DataAplicacao, CurriculoUsado, CartaApresentacao, Observacoes) VALUES (3, 3, 4, '2024-05-12', '/curriculos/carlos_mendes.pdf', '/cartas/carlos_rh.pdf', 'Aprovado para entrevista.'),
INSERT INTO Aplicacoes (CandidatoID, VagaID, StatusID, DataAplicacao, CurriculoUsado, CartaApresentacao, Observacoes) VALUES (4, 4, 5, '2024-05-14', '/curriculos/ana_lima.pdf', '/cartas/ana_engenharia.pdf', 'Não aprovado.'),
INSERT INTO Aplicacoes (CandidatoID, VagaID, StatusID, DataAplicacao, CurriculoUsado, CartaApresentacao, Observacoes) VALUES (5, 5, 3, '2024-05-15', '/curriculos/luciano_ferreira.pdf', '/cartas/luciano_nuvem.pdf', 'Agendada entrevista técnica.');

-- Inserindo na tabela Contatos
INSERT INTO Contatos (EmpresaID, Nome, Email, Telefone, Cargo, Observacoes) VALUES (1, 'Rafael Souza', 'rafael.souza@techsolutions.com.br', '(11) 3322-1122', 'Coordenador de TI', 'Responsável pelas entrevistas técnicas.'),
INSERT INTO Contatos (EmpresaID, Nome, Email, Telefone, Cargo, Observacoes) VALUES (2, 'Juliana Almeida', 'juliana.almeida@greenfoods.com.br', '(21) 4433-2211', 'Gerente de Comunicação', 'Prefere ligação às terças.'),
INSERT INTO Contatos (EmpresaID, Nome, Email, Telefone, Cargo, Observacoes) VALUES (3, 'Pedro Henrique', 'pedroh@inovarh.com.br', '(31) 5566-7788', 'Recrutador', 'Contato principal.'),
INSERT INTO Contatos (EmpresaID, Nome, Email, Telefone, Cargo, Observacoes) VALUES (4, 'Roberta Dias', 'roberta.dias@blueengenharia.com.br', '(51) 8899-0011', 'Supervisora de Obras', 'Disponível para reuniões.'),
INSERT INTO Contatos (EmpresaID, Nome, Email, Telefone, Cargo, Observacoes) VALUES (5, 'Felipe Martins', 'felipe.martins@cloudservices.com.br', '(11) 9999-8888', 'Arquiteto de Nuvem', 'Gestor técnico da vaga.');

-- Inserindo na tabela Acompanhamentos
INSERT INTO Acompanhamentos (AplicacaoID, DataAcompanhamento, TipoAcao, Observacoes, Concluido) VALUES (1, '2024-05-12', 'E-mail', 'Enviado feedback sobre currículo.', TRUE),
INSERT INTO Acompanhamentos (AplicacaoID, DataAcompanhamento, TipoAcao, Observacoes, Concluido) VALUES (2, '2024-05-14', 'Ligação', 'Agendamento de entrevista confirmado.', TRUE),
INSERT INTO Acompanhamentos (AplicacaoID, DataAcompanhamento, TipoAcao, Observacoes, Concluido) VALUES (3, '2024-05-15', 'Reunião Online', 'Entrevista técnica realizada.', TRUE),
INSERT INTO Acompanhamentos (AplicacaoID, DataAcompanhamento, TipoAcao, Observacoes, Concluido) VALUES (4, '2024-05-16', 'E-mail', 'Resultado negativo informado.', TRUE),
INSERT INTO Acompanhamentos (AplicacaoID, DataAcompanhamento, TipoAcao, Observacoes, Concluido) VALUES (5, '2024-05-17', 'Ligação', 'Próximos passos aguardando feedback.', FALSE);

-- Comandos SELECT para listar os dados das tabelas
SELECT * FROM Candidatos;
SELECT * FROM Empresas;
SELECT * FROM Vagas;
SELECT * FROM Statuses;
SELECT * FROM Aplicacoes;
SELECT * FROM Contatos;
SELECT * FROM Acompanhamentos;

