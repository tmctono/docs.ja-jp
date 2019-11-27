---
title: IMetaDataEmit2 インターフェイス
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
ms.openlocfilehash: 7ceae6f7713ab0eb1feff550838325df0ea52de2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447918"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="bc357-102">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bc357-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="bc357-103">[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)インターフェイスを拡張して、主にジェネリック型を操作できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bc357-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc357-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="bc357-104">Methods</span></span>  
  
|<span data-ttu-id="bc357-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="bc357-105">Method</span></span>|<span data-ttu-id="bc357-106">説明</span><span class="sxs-lookup"><span data-stu-id="bc357-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc357-107">DefineGenericParam メソッド</span><span class="sxs-lookup"><span data-stu-id="bc357-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="bc357-108">ジェネリック型パラメーターの定義を作成し、そのジェネリック型パラメーターへのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="bc357-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="bc357-109">DefineMethodSpec メソッド</span><span class="sxs-lookup"><span data-stu-id="bc357-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="bc357-110">メソッドのジェネリックインスタンスを作成し、その定義へのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="bc357-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="bc357-111">GetDeltaSaveSize メソッド</span><span class="sxs-lookup"><span data-stu-id="bc357-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="bc357-112">現在のエディットコンティニュセッションの変更を表すために必要なデータのサイズの差を示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc357-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="bc357-113">ResetENCLog メソッド</span><span class="sxs-lookup"><span data-stu-id="bc357-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="bc357-114">エディットコンティニュログをリセットし、新しいセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="bc357-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="bc357-115">SaveDelta メソッド</span><span class="sxs-lookup"><span data-stu-id="bc357-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="bc357-116">現在のエディットコンティニュセッションから、指定したファイルへの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="bc357-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="bc357-117">SaveDeltaToMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="bc357-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="bc357-118">現在のエディットコンティニュセッションの変更をメモリに保存します。</span><span class="sxs-lookup"><span data-stu-id="bc357-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="bc357-119">SaveDeltaToStream メソッド</span><span class="sxs-lookup"><span data-stu-id="bc357-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="bc357-120">現在のエディットコンティニュセッションから、指定されたストリームに変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="bc357-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="bc357-121">SetGenericParamProps メソッド</span><span class="sxs-lookup"><span data-stu-id="bc357-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="bc357-122">指定したトークンによって参照されるジェネリックパラメーター定義のプロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="bc357-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc357-123">要件</span><span class="sxs-lookup"><span data-stu-id="bc357-123">Requirements</span></span>  
 <span data-ttu-id="bc357-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc357-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc357-125">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="bc357-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc357-126">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc357-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc357-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc357-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc357-128">参照</span><span class="sxs-lookup"><span data-stu-id="bc357-128">See also</span></span>

- [<span data-ttu-id="bc357-129">メタデータ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bc357-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="bc357-130">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bc357-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
