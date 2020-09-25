---
title: 暗号設定の <mscorlib> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: 1788205997d0dc49df172c9dfe48faceb8fc3290
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201786"
---
# <a name="mscorlib-element-for-cryptography-settings"></a>暗号設定の \<mscorlib> 要素

[ \<cryptographySettings> 要素](cryptographysettings-element.md)が含まれています。  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<mscorlib>**  
  
## <a name="syntax"></a>構文  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  

 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  

 なし。  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|`cryptographySettings`|暗号設定を含みます。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|`configuration`|共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。|  
  
## <a name="example"></a>例  

 次の例は、要素を使用して **\<mscorlib>** 暗号化クラスを参照し、ランタイムを構成する方法を示しています。 その後、文字列 "RSA" をメソッドに渡し <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 、メソッドを使用して <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> オブジェクトを返すことができ `MyCryptoRSAClass` ます。  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [構成ファイル スキーマ](../index.md)
- [暗号化設定スキーマ](index.md)
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
- [暗号化クラスの設定](../../configure-cryptography-classes.md)
