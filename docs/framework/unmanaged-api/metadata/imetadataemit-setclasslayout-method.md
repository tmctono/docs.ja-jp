---
title: IMetaDataEmit::SetClassLayout メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c455b5196ceafef924de59e9134b89ed62455520
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737226"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="9aeb2-102">IMetaDataEmit::SetClassLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="9aeb2-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="9aeb2-103">前回の呼び出しで定義されているクラスのフィールドのレイアウトが完了すると[DefineTypeDef メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aeb2-104">構文</span><span class="sxs-lookup"><span data-stu-id="9aeb2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9aeb2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9aeb2-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9aeb2-106">[in]`mdTypeDef`クラスに配置されることを示すトークン。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="9aeb2-107">[in]パッキング サイズ:1、2、4、8 または 16 バイト数。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="9aeb2-108">パッキング サイズには、横にあるフィールド間のバイト数です。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="9aeb2-109">[in]配列の[COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)構造体、クラスのフィールドとフィールドのオフセットされている場合、クラス内でそれぞれを指定します。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="9aeb2-110">終了、配列の`mdTokenNil`します。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="9aeb2-111">[in]クラスのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9aeb2-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="9aeb2-112">Remarks</span></span>  
 <span data-ttu-id="9aeb2-113">クラスが最初に呼び出すことによって定義されている、 [imetadataemit::definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)メソッド、およびクラスのフィールドの 3 つのレイアウトのいずれかを指定する: 自動、順次、または明示的な。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="9aeb2-114">通常、自動レイアウトを使用し、ランタイムでフィールドをレイアウトする最善の方法を選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="9aeb2-115">ただし、フィールドをアンマネージ コードが使用する配置に従ってレイアウトたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="9aeb2-116">この場合、レイアウトがシーケンシャルまたは明示的のいずれかと呼び出しを選択`SetClassLayout`フィールドのレイアウトを完了します。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="9aeb2-117">シーケンシャル レイアウト:パッキング サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="9aeb2-118">本来のサイズまたはパッキング サイズより小さなオフセット フィールドのいずれかの結果のいずれかに従って、フィールドが配置されます。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="9aeb2-119">設定`rFieldOffsets`と`ulClassSize`をゼロにします。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="9aeb2-120">明示的なレイアウト:各フィールドのオフセットを指定するか、クラスのサイズとパッキング サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aeb2-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="9aeb2-121">Requirements</span></span>  
 <span data-ttu-id="9aeb2-122">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aeb2-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aeb2-123">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9aeb2-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9aeb2-124">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="9aeb2-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9aeb2-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aeb2-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aeb2-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="9aeb2-126">See also</span></span>

- [<span data-ttu-id="9aeb2-127">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9aeb2-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9aeb2-128">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9aeb2-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
