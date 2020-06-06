---
title: <oidEntry> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: 4564cf59e3b6cfbdcd9dca06cd0f966d524834de
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088546"
---
# <a name="oidentry-element"></a><span data-ttu-id="cda74-102">\<oidEntry> 要素</span><span class="sxs-lookup"><span data-stu-id="cda74-102">\<oidEntry> Element</span></span>
<span data-ttu-id="cda74-103">ASN.1 オブジェクト識別子 (OID) を表示名にマップします。</span><span class="sxs-lookup"><span data-stu-id="cda74-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**

## <a name="syntax"></a><span data-ttu-id="cda74-104">構文</span><span class="sxs-lookup"><span data-stu-id="cda74-104">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cda74-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cda74-105">Attributes and Elements</span></span>  
 <span data-ttu-id="cda74-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cda74-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cda74-107">属性</span><span class="sxs-lookup"><span data-stu-id="cda74-107">Attributes</span></span>  
  
|<span data-ttu-id="cda74-108">属性</span><span class="sxs-lookup"><span data-stu-id="cda74-108">Attribute</span></span>|<span data-ttu-id="cda74-109">説明</span><span class="sxs-lookup"><span data-stu-id="cda74-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cda74-110">**ドーナツ**</span><span class="sxs-lookup"><span data-stu-id="cda74-110">**OID**</span></span>|<span data-ttu-id="cda74-111">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="cda74-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="cda74-112">クラスによって実装されたアルゴリズムに対応する asn.1 OID を指定します。</span><span class="sxs-lookup"><span data-stu-id="cda74-112">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="cda74-113">**name**</span><span class="sxs-lookup"><span data-stu-id="cda74-113">**name**</span></span>|<span data-ttu-id="cda74-114">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="cda74-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="cda74-115">タグの**name**属性の値を指定し [\<nameEntry>](nameentry-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="cda74-115">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cda74-116">子要素</span><span class="sxs-lookup"><span data-stu-id="cda74-116">Child Elements</span></span>  
 <span data-ttu-id="cda74-117">なし。</span><span class="sxs-lookup"><span data-stu-id="cda74-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cda74-118">親要素</span><span class="sxs-lookup"><span data-stu-id="cda74-118">Parent Elements</span></span>  
  
|<span data-ttu-id="cda74-119">要素</span><span class="sxs-lookup"><span data-stu-id="cda74-119">Element</span></span>|<span data-ttu-id="cda74-120">Description</span><span class="sxs-lookup"><span data-stu-id="cda74-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cda74-121">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="cda74-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="cda74-122">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="cda74-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="cda74-123">要素が含まれてい `cryptographySettings` ます。</span><span class="sxs-lookup"><span data-stu-id="cda74-123">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="cda74-124">クラスに対する asn.1 オブジェクト識別子 (OID) マッピングが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cda74-124">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cda74-125">解説</span><span class="sxs-lookup"><span data-stu-id="cda74-125">Remarks</span></span>  
 <span data-ttu-id="cda74-126">Asn.1 オブジェクト識別子は、一部の暗号化形式でアルゴリズムを識別します。</span><span class="sxs-lookup"><span data-stu-id="cda74-126">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="cda74-127">オブジェクト識別子を、識別するアルゴリズムのフレンドリ名にマップします。</span><span class="sxs-lookup"><span data-stu-id="cda74-127">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cda74-128">例</span><span class="sxs-lookup"><span data-stu-id="cda74-128">Example</span></span>  
 <span data-ttu-id="cda74-129">次の例では、要素を使用して、 **\<oidEntry>** 160 RIPEMD ハッシュアルゴリズムのオブジェクト識別子をそのハッシュアルゴリズムの実装にマップする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cda74-129">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cda74-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="cda74-130">See also</span></span>

- [<span data-ttu-id="cda74-131">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="cda74-131">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cda74-132">暗号設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="cda74-132">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cda74-133">暗号化サービス</span><span class="sxs-lookup"><span data-stu-id="cda74-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="cda74-134">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="cda74-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="cda74-135">暗号化アルゴリズムへのオブジェクト ID の割り当て</span><span class="sxs-lookup"><span data-stu-id="cda74-135">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
