---
title: IMetaDataImport::GetMethodSemantics メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: 2cfb66203d8f2d69ea188f6913a5ef34dd74791e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503602"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="a0871-102">IMetaDataImport::GetMethodSemantics メソッド</span><span class="sxs-lookup"><span data-stu-id="a0871-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="a0871-103">指定した MethodDef トークンによって参照されるメソッドと、指定した EventProp トークンによって参照されるペアのプロパティおよびイベントの間のリレーションシップを示すフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="a0871-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0871-104">構文</span><span class="sxs-lookup"><span data-stu-id="a0871-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0871-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a0871-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="a0871-106">からセマンティックロール情報を取得するメソッドを表す MethodDef トークン。</span><span class="sxs-lookup"><span data-stu-id="a0871-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="a0871-107">からメソッドのロールを取得するための、ペアのプロパティとイベントを表すトークン。</span><span class="sxs-lookup"><span data-stu-id="a0871-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="a0871-108">入出力関連付けられているセマンティクスフラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a0871-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="a0871-109">この値は、 [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md)列挙体のビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="a0871-109">This value is a bitmask from the [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0871-110">解説</span><span class="sxs-lookup"><span data-stu-id="a0871-110">Remarks</span></span>  
 <span data-ttu-id="a0871-111">[IMetaDataEmit::D efineProperty](imetadataemit-defineproperty-method.md)メソッドは、メソッドのセマンティクスフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="a0871-111">The [IMetaDataEmit::DefineProperty](imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0871-112">要件</span><span class="sxs-lookup"><span data-stu-id="a0871-112">Requirements</span></span>  
 <span data-ttu-id="a0871-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0871-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0871-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="a0871-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0871-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a0871-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0871-116">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0871-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0871-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0871-117">See also</span></span>

- [<span data-ttu-id="a0871-118">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a0871-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a0871-119">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a0871-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
