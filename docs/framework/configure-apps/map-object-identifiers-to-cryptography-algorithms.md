---
title: 暗号化アルゴリズムへのオブジェクト ID の割り当て
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
ms.openlocfilehash: a5aebac2d392d4540581dfe7c7afff0819968ac0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912542"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="b078f-102">暗号化アルゴリズムへのオブジェクト ID の割り当て</span><span class="sxs-lookup"><span data-stu-id="b078f-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="b078f-103">デジタル署名は、あるプログラムから別のプログラムに送信されるときに、データが改ざんされないようにします。</span><span class="sxs-lookup"><span data-stu-id="b078f-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="b078f-104">通常、デジタル署名は、署名されるデータのハッシュに数学関数を適用することによって計算されます。</span><span class="sxs-lookup"><span data-stu-id="b078f-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="b078f-105">署名するハッシュ値の書式を設定すると、一部のデジタル署名アルゴリズムでは、書式設定操作の一部として asn.1 オブジェクト識別子 (OID) が追加されます。</span><span class="sxs-lookup"><span data-stu-id="b078f-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="b078f-106">OID は、ハッシュの計算に使用されたアルゴリズムを識別します。</span><span class="sxs-lookup"><span data-stu-id="b078f-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="b078f-107">アルゴリズムをオブジェクト識別子にマップして、カスタムアルゴリズムを使用するように暗号化メカニズムを拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="b078f-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="b078f-108">次の例では、オブジェクト識別子を新しいハッシュアルゴリズムにマップする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b078f-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
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
  
 <span data-ttu-id="b078f-109">[ \<OidEntry > 要素](./file-schema/cryptography/oidentry-element.md)には、2つの属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b078f-109">The [\<oidEntry> element](./file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="b078f-110">**OID**属性は、オブジェクトの識別子番号です。</span><span class="sxs-lookup"><span data-stu-id="b078f-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="b078f-111">**Name**属性は、 [ \<nameentry > 要素](./file-schema/cryptography/nameentry-element.md)の**name**属性の値です。</span><span class="sxs-lookup"><span data-stu-id="b078f-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="b078f-112">オブジェクト識別子を簡易名にマップする前に、アルゴリズム名からクラスへのマッピングが必要です。</span><span class="sxs-lookup"><span data-stu-id="b078f-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b078f-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b078f-113">See also</span></span>

- [<span data-ttu-id="b078f-114">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="b078f-114">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
- [<span data-ttu-id="b078f-115">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="b078f-115">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
