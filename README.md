# SegundoCodigo
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Portfolio de Pedro Arduengo García</title>
    <!-- Inclusión del CSS de Prism.js para el resaltado de sintaxis -->
    <link href="https://cdnjs.cloudflare.com/ajax/libs/prism/1.29.0/themes/prism-tomorrow.min.css" rel="stylesheet" />
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background-color: #333;
            color: #fff;
            padding: 10px 0;
            text-align: center;
        }
        nav ul {
            list-style: none;
            padding: 0;
        }
        nav ul li {
            display: inline;
            margin: 0 15px;
        }
        nav ul li a {
            color: #fff;
            text-decoration: none;
        }
        main {
            padding: 20px;
        }
        section {
            margin-bottom: 40px;
        }
        footer {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 10px 0;
            position: fixed;
            width: 100%;
            bottom: 0;
        }
        .contact-info {
            background-color: #fff;
            padding: 15px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        .contact-info p {
            margin: 5px 0;
        }
        .code-container {
            background-color: #2d2d2d;
            padding: 15px;
            border-radius: 5px;
            overflow-x: auto;
        }
    </style>
</head>
<body>
    <header>
        <h1>Portfolio de Pedro Arduengo García</h1>
        <!-- Navegación del sitio -->
        <nav>
            <ul>
                <li><a href="#about">Sobre Mí</a></li>
                <li><a href="#projects">Proyectos</a></li>
                <li><a href="#contact">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <!-- Sección Sobre Mí -->
        <section id="about">
            <h2>Sobre Mí</h2>
            <p>Hola, soy Pedro Arduengo García, un técnico desarrollador web con experiencia en la creación de aplicaciones web dinámicas. Me apasiona el desarrollo de soluciones eficientes y escalables utilizando las últimas tecnologías web.</p>
        </section>

        <!-- Sección de Proyectos -->
        <section id="projects">
            <h2>Proyectos</h2>
            <!-- Proyecto VotingSystem -->
            <article>
                <h3>VotingSystem</h3>
                <p>Este es un contrato inteligente en Solidity que implementa un sistema de votación sencillo, permitiendo a los usuarios proponer y votar por diferentes opciones.</p>
                <!-- Contenedor del código con resaltado de sintaxis para Solidity -->
                <div class="code-container">
                    <pre><code class="language-solidity">
// SPDX-License-Identifier: MIT
pragma solidity >=0.6.12 <0.9.0;

/**
 * @title VotingSystem
 * @dev A simple voting system that allows users to propose and vote on different options.
 */
contract VotingSystem {
    
    struct Proposal {
        string description;
        uint voteCount;
    }

    address public chairperson;
    mapping(address => bool) public voters;
    Proposal[] public proposals;

    /**
     * @dev Sets the chairperson and initializes the contract with a default proposal.
     * @param initialProposal The description of the initial proposal.
     */
    constructor(string memory initialProposal) {
        chairperson = msg.sender;
        addProposal(initialProposal);
    }

    /**
     * @dev Adds a new proposal. Only the chairperson can add proposals.
     * @param proposalDescription The description of the proposal.
     */
    function addProposal(string memory proposalDescription) public {
        require(msg.sender == chairperson, "Only the chairperson can add proposals.");
        proposals.push(Proposal({
            description: proposalDescription,
            voteCount: 0
        }));
    }

    /**
     * @dev Allows an address to be registered as a voter.
     * @param voter The address of the voter.
     */
    function registerVoter(address voter) public {
        require(msg.sender == chairperson, "Only the chairperson can register voters.");
        voters[voter] = true;
    }

    /**
     * @dev Casts a vote to a proposal. Only registered voters can vote.
     * @param proposalIndex The index of the proposal in the proposals array.
     */
    function vote(uint proposalIndex) public {
        require(voters[msg.sender], "Only registered voters can vote.");
        require(proposalIndex < proposals.length, "Invalid proposal index.");
        proposals[proposalIndex].voteCount += 1;
    }

    /**
     * @dev Returns the description and vote count of a proposal.
     * @param proposalIndex The index of the proposal in the proposals array.
     * @return description The description of the proposal.
     * @return voteCount The number of votes the proposal has received.
     */
    function getProposal(uint proposalIndex) public view returns (string memory description, uint voteCount) {
        require(proposalIndex < proposals.length, "Invalid proposal index.");
        Proposal storage proposal = proposals[proposalIndex];
        return (proposal.description, proposal.voteCount);
    }
}
                    </code></pre>
                </div>
            </article>
        </section>

        <!-- Sección de Contacto -->
        <section id="contact">
            <h2>Contacto</h2>
            <div class="contact-info">
                <p><strong>Nombre:</strong> Pedro Arduengo García</p>
                <p><strong>Teléfono:</strong> 628 588 896</p>
                <p><strong>Email:</strong> pedro.arduengo@example.com</p>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 Pedro Arduengo García. Todos los derechos reservados.</p>
    </footer>

    <!-- Inclusión de las bibliotecas de Prism.js -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/prism/1.29.0/components/prism-core.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/prism/1.29.0/components/prism-solidity.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/prism/1.29.0/plugins/autoloader/prism-autoloader.min.js"></script
::contentReference[oaicite:0]{index=0}
 
