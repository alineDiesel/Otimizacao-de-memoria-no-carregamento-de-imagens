# Otimizacao-de-memoria-no-carregamento-de-imagens
Otimização do uso de memória no carregamento de imagens na web utilizando createObjectURL e Canvas

Utilizando o createObjectURL é possível ter um ganho de desempenho do uso da memória do navegador para carregar e renderizar imagens. 
Aplicação com grande carregamento e amostra de imagens podem causar estouro de memória nos navegadores utilizando formas simples de carregamento, como: Image.onload e criando uma new <img/> no código. 
Estes problemas serão, em valor potencialmente alto, sanados utilizando o createObjectURL para gerar uma url de referência da imagem e desenhando o canvas a partir do load da imagem. 
Nem todos os problemas foram sanados utilizando este método, é possível visualizar que no navegador FF o uso da memória ainda fica em nível alto, entretanto, em testes, foi possível verificar que isto é o retono
do carregamento de imagens em grande número ou muito grandes. Mesmo através do controle global do carregamento das imagens - objeto Image, e que sejam carregadas uma a uma, o navegador FF sofre na renderização e não no carregamento ou liberação da memória através do revokeObjectURL.
Uma solução testada para este problema mas, duvidosa, é a verificação do navegador e adição do timeout para a continuação do carregamento. Não é seguro e nem indicado, mas foi o mais próximo de uma solução e redução do uso de memória. 

