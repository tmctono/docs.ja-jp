---
title: IAssemblyName インターフェイス
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d8d59ef282818dd9852d0ff8d2ec2abd40986d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097136"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="56158-102">IAssemblyName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56158-102">IAssemblyName Interface</span></span>
<span data-ttu-id="56158-103">記述して、アセンブリの一意の id の操作のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="56158-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="56158-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="56158-104">Methods</span></span>  
  
|<span data-ttu-id="56158-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="56158-105">Method</span></span>|<span data-ttu-id="56158-106">説明</span><span class="sxs-lookup"><span data-stu-id="56158-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="56158-107">Clone メソッド</span><span class="sxs-lookup"><span data-stu-id="56158-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|<span data-ttu-id="56158-108">これの簡易コピーを作成します。`IAssemblyName`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="56158-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="56158-109">Finalize メソッド</span><span class="sxs-lookup"><span data-stu-id="56158-109">Finalize Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|<span data-ttu-id="56158-110">これにより、`IAssemblyName`オブジェクト リソースを解放し、そのデストラクターが呼び出される前に、他のクリーンアップ操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="56158-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="56158-111">GetDisplayName メソッド</span><span class="sxs-lookup"><span data-stu-id="56158-111">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|<span data-ttu-id="56158-112">これによって参照されるアセンブリの人間が判読できる名前を取得`IAssemblyName`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="56158-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="56158-113">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="56158-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|<span data-ttu-id="56158-114">これによって参照されるアセンブリの単純な暗号化されていない名前を取得`IAssemblyName`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="56158-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="56158-115">GetProperty メソッド</span><span class="sxs-lookup"><span data-stu-id="56158-115">GetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|<span data-ttu-id="56158-116">指定したによって参照されるプロパティにポインターを取得します。`PropertyId`します。</span><span class="sxs-lookup"><span data-stu-id="56158-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="56158-117">GetVersion メソッド</span><span class="sxs-lookup"><span data-stu-id="56158-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|<span data-ttu-id="56158-118">これによって参照されるアセンブリのバージョン情報を取得`IAssemblyName`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="56158-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="56158-119">IsEqual メソッド</span><span class="sxs-lookup"><span data-stu-id="56158-119">IsEqual Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|<span data-ttu-id="56158-120">指定したかどうかを判断します`IAssemblyName`オブジェクトがこれと等しい`IAssemblyName`を基に、指定した比較フラグ。</span><span class="sxs-lookup"><span data-stu-id="56158-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="56158-121">SetProperty メソッド</span><span class="sxs-lookup"><span data-stu-id="56158-121">SetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|<span data-ttu-id="56158-122">指定したによって参照されるプロパティの値を設定`PropertyId`します。</span><span class="sxs-lookup"><span data-stu-id="56158-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56158-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="56158-123">Requirements</span></span>  
 <span data-ttu-id="56158-124">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56158-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56158-125">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="56158-125">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="56158-126">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="56158-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="56158-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="56158-127">See also</span></span>

- [<span data-ttu-id="56158-128">Fusion インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56158-128">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="56158-129">IAssemblyEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="56158-129">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
