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

if __name__ == "__main__":
    app.run(debug=True)
