---
title: 暗号化クラスの設定
description: コンピューター管理者が、.NET とアプリケーションで使用する既定の暗号化アルゴリズムとアルゴリズムの実装を構成する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: 5262dfca914fd5306297ea9535bcef3d2088d107
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165209"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="43180-103">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="43180-103">Configuring Cryptography Classes</span></span>

<span data-ttu-id="43180-104">Windows SDK を使用すると、コンピューター管理者は、.NET Framework および適切に記述されたアプリケーションで使用される既定の暗号化アルゴリズムおよびアルゴリズムの実装を構成できます。</span><span class="sxs-lookup"><span data-stu-id="43180-104">The Windows SDK allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="43180-105">たとえば、暗号化アルゴリズムを独自に実装する企業は、Windows SDK に付属する実装ではなく、その実装を既定値にすることができます。</span><span class="sxs-lookup"><span data-stu-id="43180-105">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="43180-106">暗号化を使用するマネージアプリケーションは、常に特定の実装に明示的にバインドすることができますが、暗号化の構成システムを使用して暗号化オブジェクトを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="43180-106">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43180-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="43180-107">In This Section</span></span>  

 [<span data-ttu-id="43180-108">暗号化クラスへのアルゴリズム名の割り当て</span><span class="sxs-lookup"><span data-stu-id="43180-108">Mapping Algorithm Names to Cryptography Classes</span></span>](map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="43180-109">アルゴリズム名を暗号クラスにマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43180-109">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="43180-110">暗号化アルゴリズムへのオブジェクト ID の割り当て</span><span class="sxs-lookup"><span data-stu-id="43180-110">Mapping Object Identifiers to Cryptography Algorithms</span></span>](map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="43180-111">オブジェクト識別子を暗号アルゴリズムにマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43180-111">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="43180-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="43180-112">Related Sections</span></span>  

 [<span data-ttu-id="43180-113">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="43180-113">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)  
 <span data-ttu-id="43180-114">Windows SDK によって提供される暗号化サービスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="43180-114">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="43180-115">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="43180-115">Cryptography Settings Schema</span></span>](./file-schema/cryptography/index.md)  
 <span data-ttu-id="43180-116">アルゴリズムの表示名を、暗号化アルゴリズムを実装するクラスに割り当てる要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="43180-116">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
