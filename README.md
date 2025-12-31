import React, { useState, useEffect } from 'react';
import { Play, DollarSign, Award, Info, Code, ExternalLink } from 'lucide-react';

export default function AdSenseRewardSite() {
  const [showAd, setShowAd] = useState(false);
  const [earnings, setEarnings] = useState(0);
  const [adCount, setAdCount] = useState(0);
  const [showInstructions, setShowInstructions] = useState(false);

  // IMPORTANTE: Substitua 'ca-pub-XXXXXXXXXX' pelo seu ID do AdSense
  const ADSENSE_ID = 'ca-pub-XXXXXXXXXX';

  const handlePlayClick = () => {
    setShowAd(true);
    
    // Simula o anúncio por 8 segundos (tempo médio de um anúncio)
    setTimeout(() => {
      setShowAd(false);
      setAdCount(prev => prev + 1);
      // Simula ganho (no AdSense real, varia de $0.01 a $0.50 por clique)
      setEarnings(prev => prev + 0.10);
    }, 8000);
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-green-600 via-emerald-600 to-teal-500 flex items-center justify-center p-4">
      <div className="max-w-2xl w-full">
        {/* Card Principal */}
        <div className="bg-white rounded-3xl shadow-2xl p-8">
          {!showAd ? (
            <>
              {/* Cabeçalho */}
              <div className="text-center mb-8">
                <div className="w-24 h-24 bg-gradient-to-br from-green-500 to-emerald-500 rounded-full mx-auto flex items-center justify-center mb-4">
                  <Award className="w-12 h-12 text-white" />
                </div>
                <h1 className="text-4xl font-bold text-gray-800 mb-2">
                  Ganhe com Anúncios
                </h1>
                <p className="text-gray-600">
                  Site monetizado com Google AdSense
                </p>
              </div>

              {/* Área de Anúncio do AdSense */}
              <div className="mb-8 bg-gray-50 rounded-xl p-6 border-2 border-dashed border-gray-300">
                <p className="text-center text-sm text-gray-500 mb-4 font-semibold">
                  📢 ESPAÇO PARA ANÚNCIO DO GOOGLE ADSENSE
                </p>
                
                {/* Aqui vai o código do AdSense */}
                <div className="bg-white rounded-lg p-8 min-h-[250px] flex items-center justify-center border border-gray-200">
                  <div className="text-center">
                    <div className="text-6xl mb-4">💰</div>
                    <p className="text-gray-600 font-medium">
                      Cole o código do AdSense aqui
                    </p>
                    <p className="text-xs text-gray-400 mt-2">
                      ID: {ADSENSE_ID}
                    </p>
                  </div>
                </div>
                
                <p className="text-center text-xs text-gray-400 mt-4">
                  Anúncio • Google AdSense
                </p>
              </div>

              {/* Estatísticas */}
              <div className="grid grid-cols-2 gap-4 mb-8">
                <div className="bg-green-50 rounded-xl p-6 text-center">
                  <DollarSign className="w-8 h-8 text-green-600 mx-auto mb-2" />
                  <p className="text-3xl font-bold text-green-600">
                    ${earnings.toFixed(2)}
                  </p>
                  <p className="text-sm text-gray-600">Ganhos Estimados</p>
                </div>
                <div className="bg-blue-50 rounded-xl p-6 text-center">
                  <Award className="w-8 h-8 text-blue-600 mx-auto mb-2" />
                  <p className="text-3xl font-bold text-blue-600">
                    {adCount}
                  </p>
                  <p className="text-sm text-gray-600">Visualizações</p>
                </div>
              </div>

              {/* Botão Principal */}
              <button
                onClick={handlePlayClick}
                className="w-full bg-gradient-to-r from-green-600 to-emerald-600 text-white font-bold py-5 px-8 rounded-full text-xl shadow-lg hover:shadow-xl transform hover:scale-105 transition-all duration-200 flex items-center justify-center gap-3 mb-4"
              >
                <Play className="w-8 h-8 fill-current" />
                VER MAIS ANÚNCIOS
              </button>

              {/* Botão Instruções */}
              <button
                onClick={() => setShowInstructions(!showInstructions)}
                className="w-full bg-gray-100 text-gray-700 font-semibold py-3 px-6 rounded-full hover:bg-gray-200 transition-all duration-200 flex items-center justify-center gap-2"
              >
                <Code className="w-5 h-5" />
                {showInstructions ? 'Ocultar' : 'Ver'} Como Conectar ao AdSense
              </button>

              {/* Instruções */}
              {showInstructions && (
                <div className="mt-6 space-y-4">
                  <div className="bg-blue-50 rounded-xl p-6">
                    <h3 className="font-bold text-gray-800 mb-4 flex items-center gap-2">
                      <Info className="w-5 h-5 text-blue-600" />
                      Como Conectar o Google AdSense (GRÁTIS)
                    </h3>
                    
                    <ol className="space-y-4 text-sm text-gray-700">
                      <li className="flex gap-3">
                        <span className="font-bold text-blue-600 flex-shrink-0">1.</span>
                        <div>
                          <strong>Criar conta no AdSense:</strong>
                          <p className="text-gray-600 mt-1">
                            Acesse <a href="https://www.google.com/adsense" target="_blank" rel="noopener" className="text-blue-600 underline">google.com/adsense</a> e crie sua conta (100% gratuito)
                          </p>
                        </div>
                      </li>
                      
                      <li className="flex gap-3">
                        <span className="font-bold text-blue-600 flex-shrink-0">2.</span>
                        <div>
                          <strong>Adicionar seu site:</strong>
                          <p className="text-gray-600 mt-1">
                            No painel do AdSense, adicione a URL do seu site
                          </p>
                        </div>
                      </li>
                      
                      <li className="flex gap-3">
                        <span className="font-bold text-blue-600 flex-shrink-0">3.</span>
                        <div>
                          <strong>Copiar código de anúncio:</strong>
                          <p className="text-gray-600 mt-1">
                            No AdSense, crie uma unidade de anúncio e copie o código
                          </p>
                        </div>
                      </li>
                      
                      <li className="flex gap-3">
                        <span className="font-bold text-blue-600 flex-shrink-0">4.</span>
                        <div>
                          <strong>Colar no HTML:</strong>
                          <p className="text-gray-600 mt-1 bg-gray-800 text-green-400 p-3 rounded font-mono text-xs overflow-x-auto">
                            {`<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-SEU_ID"
     crossorigin="anonymous"></script>`}
                          </p>
                        </div>
                      </li>
                      
                      <li className="flex gap-3">
                        <span className="font-bold text-blue-600 flex-shrink-0">5.</span>
                        <div>
                          <strong>Hospedar o site:</strong>
                          <p className="text-gray-600 mt-1">
                            Use Netlify, Vercel ou GitHub Pages (todos GRATUITOS)
                          </p>
                        </div>
                      </li>
                      
                      <li className="flex gap-3">
                        <span className="font-bold text-blue-600 flex-shrink-0">6.</span>
                        <div>
                          <strong>Aguardar aprovação:</strong>
                          <p className="text-gray-600 mt-1">
                            Google analisa seu site (pode levar alguns dias)
                          </p>
                        </div>
                      </li>
                    </ol>
                  </div>

                  <div className="bg-yellow-50 rounded-xl p-6 border-2 border-yellow-200">
                    <h4 className="font-bold text-gray-800 mb-2">⚠️ Importante:</h4>
                    <ul className="space-y-2 text-sm text-gray-700">
                      <li>• Você precisa ter TRÁFEGO REAL (visitantes de verdade)</li>
                      <li>• Não clique nos próprios anúncios (Google bane)</li>
                      <li>• Conteúdo original e de qualidade aumenta aprovação</li>
                      <li>• Ganhos variam de $0.01 a $1+ por clique</li>
                    </ul>
                  </div>

                  <div className="bg-green-50 rounded-xl p-6">
                    <h4 className="font-bold text-gray-800 mb-2">✅ Vantagens do AdSense:</h4>
                    <ul className="space-y-2 text-sm text-gray-700">
                      <li>• 100% GRATUITO para começar</li>
                      <li>• Não precisa pagar taxa de loja</li>
                      <li>• Funciona em qualquer site</li>
                      <li>• Pagamento direto na sua conta bancária</li>
                    </ul>
                  </div>
                </div>
              )}

              {/* Info Card */}
              <div className="mt-6 bg-gradient-to-r from-green-50 to-emerald-50 rounded-xl p-4 flex items-start gap-3 border border-green-200">
                <ExternalLink className="w-5 h-5 text-green-600 flex-shrink-0 mt-0.5" />
                <div className="text-left">
                  <p className="text-sm text-gray-800 font-semibold mb-1">
                    Monetize seu site com Google AdSense
                  </p>
                  <p className="text-xs text-gray-600">
                    Totalmente gratuito • Sem taxas • Pagamento garantido pelo Google
                  </p>
                </div>
              </div>
            </>
          ) : (
            <>
              {/* Tela de Anúncio */}
              <div className="py-16 text-center">
                <div className="animate-pulse mb-8">
                  <div className="w-24 h-24 bg-gradient-to-br from-yellow-400 to-orange-500 rounded-full mx-auto flex items-center justify-center mb-4">
                    <Play className="w-12 h-12 text-white" />
                  </div>
                </div>
                
                <h2 className="text-3xl font-bold text-gray-800 mb-6">
                  Anúncio em Exibição
                </h2>
                
                {/* Simulação de Anúncio em Tela Cheia */}
                <div className="bg-gray-100 rounded-2xl p-12 mb-8">
                  <div className="w-full h-64 bg-gradient-to-br from-gray-300 to-gray-400 rounded-xl flex items-center justify-center">
                    <div className="text-center">
                      <div className="text-6xl mb-4">📺</div>
                      <p className="text-gray-600 font-semibold text-xl">
                        ANÚNCIO DO GOOGLE ADSENSE
                      </p>
                      <p className="text-xs text-gray-500 mt-2">
                        Anúncio real aparecerá aqui
                      </p>
                    </div>
                  </div>
                </div>
                
                <div className="flex items-center justify-center gap-3 text-gray-600">
                  <span className="inline-block w-3 h-3 bg-green-500 rounded-full animate-pulse"></span>
                  <span className="text-lg">Aguarde o anúncio terminar...</span>
                </div>
              </div>
            </>
          )}
        </div>

        {/* Footer Info */}
        <div className="mt-6 text-center text-white text-sm bg-white/10 backdrop-blur-sm rounded-xl p-4">
          <p className="font-semibold mb-2">💡 Dica Profissional:</p>
          <p className="text-xs opacity-90">
            Quanto mais visitantes seu site tiver, mais você ganha com AdSense. 
            Crie conteúdo de qualidade e divulgue nas redes sociais!
          </p>
        </div>
      </div>
    </div>
  );
}
