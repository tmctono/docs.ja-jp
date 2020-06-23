---
title: 暗号化アルゴリズムへのオブジェクト ID の割り当て
description: XML 構成ファイルの oidEntry および nameEntry 要素を使用して、.NET で暗号化アルゴリズムにオブジェクト識別子 (OID) をマップする方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
ms.openlocfilehash: e22510014071455b83ba28cd82690b5ecdce9bc9
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2020
ms.locfileid: "85142005"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="3d792-103">暗号化アルゴリズムへのオブジェクト ID の割り当て</span><span class="sxs-lookup"><span data-stu-id="3d792-103">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="3d792-104">デジタル署名は、あるプログラムから別のプログラムに送信されるときに、データが改ざんされないようにします。</span><span class="sxs-lookup"><span data-stu-id="3d792-104">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="3d792-105">通常、デジタル署名は、署名されるデータのハッシュに数学関数を適用することによって計算されます。</span><span class="sxs-lookup"><span data-stu-id="3d792-105">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="3d792-106">署名するハッシュ値の書式を設定すると、一部のデジタル署名アルゴリズムでは、書式設定操作の一部として asn.1 オブジェクト識別子 (OID) が追加されます。</span><span class="sxs-lookup"><span data-stu-id="3d792-106">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="3d792-107">OID は、ハッシュの計算に使用されたアルゴリズムを識別します。</span><span class="sxs-lookup"><span data-stu-id="3d792-107">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="3d792-108">アルゴリズムをオブジェクト識別子にマップして、カスタムアルゴリズムを使用するように暗号化メカニズムを拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="3d792-108">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="3d792-109">次の例では、オブジェクト識別子を新しいハッシュアルゴリズムにマップする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3d792-109">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="3d792-110">[ \<oidEntry> 要素](./file-schema/cryptography/oidentry-element.md)には、2つの属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d792-110">The [\<oidEntry> element](./file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="3d792-111">**OID**属性は、オブジェクトの識別子番号です。</span><span class="sxs-lookup"><span data-stu-id="3d792-111">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="3d792-112">**Name**属性は、 [ \<nameEntry> 要素](./file-schema/cryptography/nameentry-element.md)の**name**属性の値です。</span><span class="sxs-lookup"><span data-stu-id="3d792-112">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="3d792-113">オブジェクト識別子を簡易名にマップする前に、アルゴリズム名からクラスへのマッピングが必要です。</span><span class="sxs-lookup"><span data-stu-id="3d792-113">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d792-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d792-114">See also</span></span>

- [<span data-ttu-id="3d792-115">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="3d792-115">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
- [<span data-ttu-id="3d792-116">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="3d792-116">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
