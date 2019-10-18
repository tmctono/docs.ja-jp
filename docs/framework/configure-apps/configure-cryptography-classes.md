---
title: 暗号化クラスの設定
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: e53f4c5c9e24fb25b43b7f27b80ab984214eeac2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927768"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="ab983-102">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="ab983-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="ab983-103">Windows SDK を使用すると、コンピューター管理者は、.NET Framework および適切に記述されたアプリケーションで使用される既定の暗号化アルゴリズムおよびアルゴリズムの実装を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ab983-103">The Windows SDK allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="ab983-104">たとえば、暗号化アルゴリズムを独自に実装する企業は、Windows SDK に付属する実装ではなく、その実装を既定値にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab983-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="ab983-105">暗号化を使用するマネージアプリケーションは、常に特定の実装に明示的にバインドすることができますが、暗号化の構成システムを使用して暗号化オブジェクトを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ab983-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab983-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ab983-106">In This Section</span></span>  
 [<span data-ttu-id="ab983-107">暗号化クラスへのアルゴリズム名の割り当て</span><span class="sxs-lookup"><span data-stu-id="ab983-107">Mapping Algorithm Names to Cryptography Classes</span></span>](map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="ab983-108">アルゴリズム名を暗号クラスにマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab983-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="ab983-109">暗号化アルゴリズムへのオブジェクト ID の割り当て</span><span class="sxs-lookup"><span data-stu-id="ab983-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="ab983-110">オブジェクト識別子を暗号アルゴリズムにマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab983-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ab983-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab983-111">Related Sections</span></span>  
 [<span data-ttu-id="ab983-112">暗号化サービス</span><span class="sxs-lookup"><span data-stu-id="ab983-112">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)  
 <span data-ttu-id="ab983-113">Windows SDK によって提供される暗号化サービスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab983-113">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="ab983-114">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="ab983-114">Cryptography Settings Schema</span></span>](./file-schema/cryptography/index.md)  
 <span data-ttu-id="ab983-115">アルゴリズムの表示名を、暗号化アルゴリズムを実装するクラスに割り当てる要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab983-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
