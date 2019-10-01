---
title: 暗号設定スキーマ
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: 474c3274bfba6803ebb17289f138251d755250e4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699804"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="1efa4-102">暗号設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="1efa4-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="1efa4-103">暗号設定スキーマには、アルゴリズムの表示名を、暗号化アルゴリズムを実装するクラスに割り当てる方法を指定する要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1efa4-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
[<span data-ttu-id="1efa4-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1efa4-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="1efa4-105">&nbsp; @ no__t-1[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1efa4-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="1efa4-106">&nbsp; @ no__t-1 @ no__t @ no__t-3[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="1efa4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="1efa4-107">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<cryptoNameMapping >** を行います。](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="1efa4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>  
<span data-ttu-id="1efa4-108">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0cryptoClasses (10) >** ](cryptoclasses-element.md)</span><span class="sxs-lookup"><span data-stu-id="1efa4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>  
<span data-ttu-id="1efa4-109">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 @ no__t @ no__t @ no__t-7 @ no__t-8 @-9[ **&nbsp;2cryptoClass** (&) >](cryptoclass-element.md)</span><span class="sxs-lookup"><span data-stu-id="1efa4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)</span></span>  
<span data-ttu-id="1efa4-110">&nbsp; @ no__t @ no__t @ no__t @ no__t @ no__t @ no__t-6 @-7[ **&nbsp;0nameEntry > を入力**します。](nameentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="1efa4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)</span></span>  
<span data-ttu-id="1efa4-111">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5[ **\<oidMap >** を行います。](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="1efa4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>  
<span data-ttu-id="1efa4-112">&nbsp; @ no__t-1 @ no__t @ no__t @ no__t-5 @ no__t-6[ **\<oidEntry >** します。](oidentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="1efa4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)</span></span>  
  
|<span data-ttu-id="1efa4-113">要素</span><span class="sxs-lookup"><span data-stu-id="1efa4-113">Element</span></span>|<span data-ttu-id="1efa4-114">説明</span><span class="sxs-lookup"><span data-stu-id="1efa4-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1efa4-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="1efa4-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="1efa4-116">**\<nameEntry>** 要素内の表示名へのマッピングを持つ暗号化クラスのリストを含みます。</span><span class="sxs-lookup"><span data-stu-id="1efa4-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="1efa4-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="1efa4-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="1efa4-118">**\<nameEntry>** 要素内の表示名へのマッピングを持つ暗号化クラスを含みます。</span><span class="sxs-lookup"><span data-stu-id="1efa4-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="1efa4-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="1efa4-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="1efa4-120">暗号設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="1efa4-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="1efa4-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="1efa4-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="1efa4-122">表示名へのクラスのマッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="1efa4-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="1efa4-123"> **\<mscorlib>** 要素、暗号化設定用</span><span class="sxs-lookup"><span data-stu-id="1efa4-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="1efa4-124">**\<cryptographySettings >** 要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="1efa4-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="1efa4-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="1efa4-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="1efa4-126">アルゴリズムの表示名にクラス名をマップして、1 つのクラスが多くの表示名を持つことを許可します。</span><span class="sxs-lookup"><span data-stu-id="1efa4-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="1efa4-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="1efa4-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="1efa4-128">ASN.1 オブジェクト識別子 (OID) を表示名にマップします。</span><span class="sxs-lookup"><span data-stu-id="1efa4-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="1efa4-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="1efa4-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="1efa4-130">クラスへの ASN.1 OID マッピングを含みます。</span><span class="sxs-lookup"><span data-stu-id="1efa4-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1efa4-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="1efa4-131">See also</span></span>

- [<span data-ttu-id="1efa4-132">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="1efa4-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1efa4-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="1efa4-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
