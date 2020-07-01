# Product-feed-For-Amazon
Send produt feed for amazon


<?xml version = "1.0" encoding = "iso-8859-1"?>
		<AmazonEnvelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
		 xsi:noNamespaceSchemaLocation="amzn-envelope.xsd">
			<Header>
				<DocumentVersion>1.01</DocumentVersion>
				<MerchantIdentifier>Indentificador do Vendedor</MerchantIdentifier>
			</Header>
			<MessageType>Product</MessageType> //O tipo de payload, que no caso é Payload de Produto
			<PurgeAndReplace>false</PurgeAndReplace> //Padrão da Amazon deixa esse campo falso, pra não ocorrer problemas
			<Message>
				<MessageID>1</MessageID> // O messageID vai ser sempre 1 por padrão da Amazon
				<OperationType>Update</OperationType> // OperationType sempre update! Este payload serve tanto pra criação, como update!
				<Product>
					<SKU>1514</SKU> // Indentificador do seu produto
					 <StandardProductID>
        				<Type>EAN</Type>// EAN do produto
        				<Value>Código EAN</Value> // Código do EAN
      				</StandardProductID>
					<DescriptionData>
						<Title>Título</Title> // Titulo do seu produto 
						<Brand>Marca</Brand> // Marca do produto
						<Description>Descrição</Description> // Descrição
						<ItemDimensions> // As Dimensões do produto
							<Length unitOfMeasure="CM">5545</Length> //unitOfMeasure serve para diferenciar Centimetro de Kilos 
                           	<Width unitOfMeasure="CM">55</Width>
                          	<Height unitOfMeasure="CM">5424</Height>
                          	<Weight unitOfMeasure="KG">54</Weight>
						</ItemDimensions>
                        <MSRP currency="BRL">Preço</MSRP> // O preço deve ser enviado assim, se vocÊ for vender no comércia brasileiro!
						<Manufacturer>Criadora do Produto</Manufacturer> //Criadora do Produto
						<SearchTerms>Nome de como vai ser pesquisado na Amazon</SearchTerms>
						<ItemType>Tipo de produto</ItemType> // Tipo de produto, se é um computador ou celular por exemplo	
						<RecommendedBrowseNode>60583031</RecommendedBrowseNode> //O número dentro da tag é padrão, pois vai reconhecer teu Navegador!				
					</DescriptionData>
				<ProductData> // ProductData é a categoria que seu produto vai se encaixar! não é obrigado enviar muita informação. Só o necessário
					<Beauty>
	 				     <ProductType> //ProductType é padrão então sempre você vai coloca-lo abaixo da tua categoria!
						<BeautyMisc> //Está é uma das categorias que existe na Amazon. Está é a categoria "Beleza"!
							<VariationData>
                                                    		<Parentage>child</Parentage> 
                                                    		<VariationTheme>Size</VariationTheme>
                                                    		<Size>50cm</Size>
                                            		</VariationData>
							 <UnitCount unitOfMeasure="oz">5</UnitCount> // Quantidade do produto que você está enviando
						</BeautyMisc>
					     </ProductType>
			               </Beauty>
				</ProductData>
			</Product>
		</Message>
    </AmazonEnvelope>
    
  
