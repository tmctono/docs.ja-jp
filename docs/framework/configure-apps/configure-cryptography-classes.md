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
ms.openlocfilehash: b5c1178519601d7dcb7c5b3014f413b6436746fb
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816159"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="6d235-102">暗号化クラスの設定</span><span class="sxs-lookup"><span data-stu-id="6d235-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="6d235-103">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]コンピューターの管理者は、既定の暗号アルゴリズムと、.NET Framework と適切に記述されたアプリケーションを使用するアルゴリズムの実装を構成します。</span><span class="sxs-lookup"><span data-stu-id="6d235-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="6d235-104">などを暗号アルゴリズムの独自の実装を持つ企業では、Windows SDK の実装ではなく既定の出荷に実装するを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="6d235-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="6d235-105">暗号化を使用するマネージ アプリケーションは、特定の実装にバインドするように常に選択できますが、crypto の構成システムを使用して暗号化オブジェクトを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6d235-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d235-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6d235-106">In This Section</span></span>  
 [<span data-ttu-id="6d235-107">暗号化クラスへのアルゴリズム名の割り当て</span><span class="sxs-lookup"><span data-stu-id="6d235-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="6d235-108">暗号化クラスに、アルゴリズム名をマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d235-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="6d235-109">暗号化アルゴリズムへのオブジェクト ID の割り当て</span><span class="sxs-lookup"><span data-stu-id="6d235-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="6d235-110">暗号化アルゴリズムにオブジェクト識別子をマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d235-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6d235-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d235-111">Related Sections</span></span>  
 [<span data-ttu-id="6d235-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="6d235-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="6d235-113">Windows SDK によって提供される暗号化サービスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="6d235-113">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="6d235-114">暗号化設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="6d235-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="6d235-115">アルゴリズムの表示名を、暗号化アルゴリズムを実装するクラスに割り当てる要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d235-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>
