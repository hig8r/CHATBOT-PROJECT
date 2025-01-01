from flask import Flask

app = Flask(__name__)

# Página inicial
@app.route("/")
def home():
    return """
    <h1>Bem-vindo ao Chatbot de Suporte Técnico!</h1>
    <p>Como podemos te ajudar hoje? Escolha a categoria do seu equipamento:</p>
    <ol>
       <li><a href="/Meios_de_Pagamentos">Meios de Pagamento (SmartPOS, MPOS, POS, PIN Pad)</a></li>
       <li><a href="/Outros">Outros</a></li>
    </ol>
    """

# Página: Meios de Pagamento
@app.route("/Meios_de_Pagamentos")
def meios_de_pagamentos():
    return """
    <h1>Meios de Pagamento</h1>
    <p>Escolha o modelo do equipamento:</p>
    <ol>
        <li><a href="/GPOS">GPOS</a></li>
        <li><a href="/MPOS">MPOS</a></li>
        <li><a href="/PinPad">PinPad - PPC</a></li>
        <li><a href="/SmartPOS">SmartPOS</a></li>
    </ol>
    """

# Página: SmartPOS
@app.route("/SmartPOS")
def smartpos():
    return """
    <h1>SmartPOS</h1>
    <p>Selecione o problema enfrentado:</p>
    <ol>
        <li><a href="/Equipamento_Bloqueado">Equipamento Bloqueado</a></li>
        <li><a href="/Equipamento_Nao_Liga">Equipamento Não Liga</a></li>
        <li><a href="/Outros_Problemas">Nenhuma das opções</a></li>
        <li><a href="/Tamper_Detectado">TAMPER Detectado</a></li>
    </ol>
    """

# Página: Equipamento Não Liga
@app.route("/Equipamento_Nao_Liga")
def equipamento_nao_liga():
    return """
    <h1>Equipamento Não Liga</h1>
    <p>Olá! Vamos resolver isso juntos! 😊 Aqui estão as possíveis causas:</p>
    <ul>
        <li>Bateria descarregada ou com defeito</li>
        <li>Botão de ligar ou hardware interno com falhas</li>
        <li>Fonte de energia desconectada ou com problemas</li>
    </ul>
    <p>Agora que sabemos as causas, siga estas etapas para testar:</p>
    <p>Conecte o equipamento a uma fonte de energia confiável e veja se a luz do carregador acende.</p>
    <ol>
        <li><a href="/Carregador_Funciona">Sim, o carregador funciona</a></li>
        <li><a href="/Carregador_Nao_Funciona">Não, o carregador não funciona</a></li>
    </ol>
    """

# Página: Carregador Funciona
@app.route("/Carregador_Funciona")
def carregador_funciona():
    return """
    <h1>Carregador Funciona</h1>
    <p>Deixe o equipamento carregando por 30 minutos e tente ligá-lo novamente.</p>
    <p>O equipamento ligou?</p>
    <ol>
        <li><a href="/Ligou">Sim, ligou!</a></li>
        <li><a href="/Nao_Ligou">Não, não ligou.</a></li>
    </ol>
    """

# Página: Carregador Não Funciona
@app.route("/Carregador_Nao_Funciona")
def carregador_nao_funciona():
    return """
    <h1>Carregador Não Funciona</h1>
    <p>Parece que o problema está no carregador ou na tomada.</p>
    <ol>
        <li>Conecte o equipamento em uma outra tomada.</li>
        <li>Tente trocar o cabo ou o carregador por outro, se tiver disponível.</li>
    </ol>
    <p>Após isso, a luz do carregador acendeu?</p>
    <ol>
        <li><a href="/Carregador_Funciona">Sim, agora funciona</a></li>
        <li><a href="/Assistencia">Não, continua não funcionando</a></li>
    </ol>
    """

# Página: Equipamento Ligou
@app.route("/Ligou")
def ligou():
    return """
    <h1>Equipamento Ligou</h1>
    <p>Ótimo! Parece que o problema foi resolvido. 😊</p>
    <p>Se precisar de mais ajuda, é só me chamar novamente!</p>
    <p><a href="/">Voltar à página inicial</a></p>
    """

# Página: Equipamento Não Ligou
@app.route("/Nao_Ligou")
def nao_ligou():
    return """
    <h1>Equipamento Não Ligou</h1>
    <p>Vamos testar o botão de ligar:</p>
    <ol>
        <li>Espere alguns segundos para ver se o equipamento responde.</li>
        <li>Pressione e segure o botão de ligar por 10 segundos.</li>
    </ol>
    <p>O equipamento ligou ou mostrou algum sinal de resposta?</p>
    <ol>
        <li><a href="/Ligou">Sim</a></li>
        <li><a href="/Assistencia">Não</a></li>
    </ol>
    """

# Página: Assistência Técnica
@app.route("/Assistencia")
def assistencia():
    return """
    <h1>Assistência Técnica</h1>
    <p>Infelizmente, o problema parece ser interno. 😕</p>
    <p>Será necessário enviar o equipamento para assistência técnica. Clique no link abaixo para registrar o envio:</p>
    <p><a href="https://www.gertec.com.br/encontre-uma-assistencia-tecnica/">Registrar Envio</a></p>
    <p><a href="/">Voltar à página inicial</a></p>
    """

# Página: Equipamento Bloqueado
@app.route("/Equipamento_Bloqueado")
def equipamento_bloqueado():
    return """
    <h1>Equipamento Bloqueado</h1>
    <p>Vamos verificar as possíveis causas e corrigir o problema:</p>
    <ol>
        <li>O equipamento está conectado à internet? <a href="/Sim_Internet">Sim</a> | <a href="/Nao_Internet">Não</a></li>
    </ol>
    """

# Página: TAMPER Detectado
@app.route("/Tamper_Detectado")
def tamper_detectado():
    return """
    <h1>TAMPER Detectado</h1>
    <p>Essa mensagem indica que o sistema de segurança foi ativado.</p>
    <p>Possíveis causas:</p>
    <ol>
        <li>Impacto ou vibração</li>
        <li>Problema no firmware ou sensores internos</li>
        <li>Violação física (tentativa de desmontagem)</li>
    </ol>
    <p>Infelizmente, será necessário enviar o equipamento para assistência técnica.</p>
    <p><a href="https://www.gertec.com.br/encontre-uma-assistencia-tecnica/">Registrar Envio</a></p>
    <p><a href="/">Voltar à página inicial</a></p>
    """

if __name__ == "__main__":
    app.run(debug=True)
