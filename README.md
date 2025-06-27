-- INÍCIO
-- Listando todos os candidatos
SELECT * FROM Candidatos;

-- Listando todas as empresas
SELECT * FROM Empresas;

-- Listando todas as vagas
SELECT * FROM Vagas;

-- Listando todos os status possíveis
SELECT * FROM Statuses;

-- Listando todas as aplicações (candidaturas)
SELECT * FROM Aplicacoes;

-- Listando todos os contatos das empresas
SELECT * FROM Contatos;

-- Listando todos os acompanhamentos das aplicações
SELECT * FROM Acompanhamentos;

-- 1. Listar empresas em ordem alfabética 

SELECT * FROM Empresas
ORDER BY Nome ASC;

-- 2.  Contar quantas vagas existem cadastradas

SELECT COUNT(*) AS TotalVagas FROM Vagas;

-- 3. Listar apenas os acompanhamentos pendentes
SELECT * FROM Acompanhamentos
WHERE Concluido = FALSE;


--4. Listar todas as aplicações com detalhes do candidato, vaga e empresa
SELECT 
    a.AplicacaoID,
    CONCAT(c.Nome, ' ', c.Sobrenome) AS Candidato,
    v.Titulo AS Vaga,
    e.Nome AS Empresa,
    s.NomeStatus AS StatusAtual
FROM Aplicacoes a
INNER JOIN Candidatos c ON a.CandidatoID = c.CandidatoID
INNER JOIN Vagas v ON a.VagaID = v.VagaID
INNER JOIN Empresas e ON v.EmpresaID = e.EmpresaID
INNER JOIN Statuses s ON a.StatusID = s.StatusID;

--5. Listar aplicacoes de um candidato especifico nome Carlos Mendes 
SELECT 
    a.AplicacaoID,
    v.Titulo AS Vaga,
    e.Nome AS Empresa,
    s.NomeStatus AS Status,
    a.DataAplicacao
FROM Aplicacoes a
INNER JOIN Candidatos c ON a.CandidatoID = c.CandidatoID
INNER JOIN Vagas v ON a.VagaID = v.VagaID
INNER JOIN Empresas e ON v.EmpresaID = e.EmpresaID
INNER JOIN Statuses s ON a.StatusID = s.StatusID
WHERE c.Nome = 'Carlos' AND c.Sobrenome = 'Mendes'
ORDER BY a.DataAplicacao DESC;
