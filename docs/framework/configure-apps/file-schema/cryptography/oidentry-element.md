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
ms.openlocfilehash: cbdf6150010ca2dace3f0610d9caa90c2bf52746
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921056"
---
# <a name="oidentry-element"></a><span data-ttu-id="f27ea-102">\<oidEntry > 要素</span><span class="sxs-lookup"><span data-stu-id="f27ea-102">\<oidEntry> Element</span></span>
<span data-ttu-id="f27ea-103">ASN.1 オブジェクト識別子 (OID) を表示名にマップします。</span><span class="sxs-lookup"><span data-stu-id="f27ea-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
 <span data-ttu-id="f27ea-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f27ea-104">\<configuration></span></span>  
<span data-ttu-id="f27ea-105">\<mscorlib ></span><span class="sxs-lookup"><span data-stu-id="f27ea-105">\<mscorlib></span></span>  
<span data-ttu-id="f27ea-106">\<cryptographySettings ></span><span class="sxs-lookup"><span data-stu-id="f27ea-106">\<cryptographySettings></span></span>  
<span data-ttu-id="f27ea-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="f27ea-107">\<oidMap></span></span>  
<span data-ttu-id="f27ea-108">\<oidEntry ></span><span class="sxs-lookup"><span data-stu-id="f27ea-108">\<oidEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f27ea-109">構文</span><span class="sxs-lookup"><span data-stu-id="f27ea-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f27ea-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f27ea-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f27ea-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f27ea-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f27ea-112">属性</span><span class="sxs-lookup"><span data-stu-id="f27ea-112">Attributes</span></span>  
  
|<span data-ttu-id="f27ea-113">属性</span><span class="sxs-lookup"><span data-stu-id="f27ea-113">Attribute</span></span>|<span data-ttu-id="f27ea-114">説明</span><span class="sxs-lookup"><span data-stu-id="f27ea-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f27ea-115">**ドーナツ**</span><span class="sxs-lookup"><span data-stu-id="f27ea-115">**OID**</span></span>|<span data-ttu-id="f27ea-116">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="f27ea-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="f27ea-117">クラスによって実装されたアルゴリズムに対応する asn.1 OID を指定します。</span><span class="sxs-lookup"><span data-stu-id="f27ea-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="f27ea-118">**name**</span><span class="sxs-lookup"><span data-stu-id="f27ea-118">**name**</span></span>|<span data-ttu-id="f27ea-119">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="f27ea-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="f27ea-120">Nameentry > タグの**name**属性[の値を指定します。 \<](nameentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="f27ea-120">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f27ea-121">子要素</span><span class="sxs-lookup"><span data-stu-id="f27ea-121">Child Elements</span></span>  
 <span data-ttu-id="f27ea-122">なし。</span><span class="sxs-lookup"><span data-stu-id="f27ea-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f27ea-123">親要素</span><span class="sxs-lookup"><span data-stu-id="f27ea-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f27ea-124">要素</span><span class="sxs-lookup"><span data-stu-id="f27ea-124">Element</span></span>|<span data-ttu-id="f27ea-125">説明</span><span class="sxs-lookup"><span data-stu-id="f27ea-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f27ea-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f27ea-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="f27ea-127">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="f27ea-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="f27ea-128">`cryptographySettings`要素を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="f27ea-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="f27ea-129">クラスに対する asn.1 オブジェクト識別子 (OID) マッピングが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f27ea-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f27ea-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="f27ea-130">Remarks</span></span>  
 <span data-ttu-id="f27ea-131">Asn.1 オブジェクト識別子は、一部の暗号化形式でアルゴリズムを識別します。</span><span class="sxs-lookup"><span data-stu-id="f27ea-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="f27ea-132">オブジェクト識別子を、識別するアルゴリズムのフレンドリ名にマップします。</span><span class="sxs-lookup"><span data-stu-id="f27ea-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f27ea-133">例</span><span class="sxs-lookup"><span data-stu-id="f27ea-133">Example</span></span>  
 <span data-ttu-id="f27ea-134">次の例は、  **\<oidEntry >** 要素を使用して、RIPEMD 160 ハッシュアルゴリズムのオブジェクト識別子をそのハッシュアルゴリズムの実装にマップする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f27ea-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f27ea-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="f27ea-135">See also</span></span>

- [<span data-ttu-id="f27ea-136">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="f27ea-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f27ea-137">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f27ea-137">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f27ea-138">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="f27ea-138">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="f27ea-139">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="f27ea-139">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="f27ea-140">暗号化アルゴリズムへのオブジェクト ID の割り当て</span><span class="sxs-lookup"><span data-stu-id="f27ea-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
