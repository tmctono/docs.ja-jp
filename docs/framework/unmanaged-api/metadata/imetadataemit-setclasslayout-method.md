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
ms.openlocfilehash: e855868d18fc6cffdd5d92cfa401606caf45b76c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177569"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="ccccf-102">IMetaDataEmit::SetClassLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="ccccf-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="ccccf-103">[DefineTypeDef メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)の前の呼び出しによって定義されたクラスのフィールドのレイアウトを完了します。</span><span class="sxs-lookup"><span data-stu-id="ccccf-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccccf-104">構文</span><span class="sxs-lookup"><span data-stu-id="ccccf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccccf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ccccf-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ccccf-106">[in]レイアウト`mdTypeDef`するクラスを指定するトークン。</span><span class="sxs-lookup"><span data-stu-id="ccccf-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="ccccf-107">[in]パッキング サイズ: 1、2、4、8 または 16 バイト。</span><span class="sxs-lookup"><span data-stu-id="ccccf-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="ccccf-108">パッキング・サイズは、隣接するフィールド間のバイト数です。</span><span class="sxs-lookup"><span data-stu-id="ccccf-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="ccccf-109">[in]COR_FIELD_OFFSET[構造体の](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md)配列で、各構造体はクラスのフィールドとクラス内のフィールドのオフセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccccf-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="ccccf-110">配列を`mdTokenNil`で終了します。</span><span class="sxs-lookup"><span data-stu-id="ccccf-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="ccccf-111">[in]クラスのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="ccccf-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccccf-112">解説</span><span class="sxs-lookup"><span data-stu-id="ccccf-112">Remarks</span></span>  
 <span data-ttu-id="ccccf-113">このクラスは、最初は[IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)メソッドを呼び出し、クラスのフィールドに対して自動、順次、または明示的な 3 つのレイアウトのいずれかを指定することによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="ccccf-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="ccccf-114">通常は自動レイアウトを使用し、実行時にフィールドをレイアウトする最適な方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="ccccf-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="ccccf-115">ただし、アンマネージ コードで使用される配置に従ってフィールドをレイアウトする場合があります。</span><span class="sxs-lookup"><span data-stu-id="ccccf-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="ccccf-116">この場合は、シーケンシャルレイアウトまたは明示的レイアウトを`SetClassLayout`選択し、フィールドのレイアウトを完了するために呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ccccf-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="ccccf-117">シーケンシャルレイアウト: 梱包サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccccf-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="ccccf-118">フィールドは、自然なサイズまたはパッキング サイズのいずれかに従って配置されます。</span><span class="sxs-lookup"><span data-stu-id="ccccf-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="ccccf-119">0 `rFieldOffsets` `ulClassSize`に設定します。</span><span class="sxs-lookup"><span data-stu-id="ccccf-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="ccccf-120">明示的なレイアウト: 各フィールドのオフセットを指定するか、クラスサイズとパッキングサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccccf-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccccf-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="ccccf-121">Requirements</span></span>  
 <span data-ttu-id="ccccf-122">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccccf-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccccf-123">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="ccccf-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ccccf-124">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccccf-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccccf-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccccf-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccccf-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccccf-126">See also</span></span>

- [<span data-ttu-id="ccccf-127">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ccccf-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ccccf-128">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ccccf-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
