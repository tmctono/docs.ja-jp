---
title: IMetaDataEmit::SetMethodProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
ms.openlocfilehash: 57f6de1f7edf7c75a3f96cb2bf9fb98fdbd6f65e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007859"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="63a6f-102">IMetaDataEmit::SetMethodProps メソッド</span><span class="sxs-lookup"><span data-stu-id="63a6f-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="63a6f-103">[IMetaDataEmit::D efinemethod](imetadataemit-definemethod-method.md)の前の呼び出しで定義されたメソッドの、指定した相対仮想アドレスに格納されている機能を設定または更新します。</span><span class="sxs-lookup"><span data-stu-id="63a6f-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63a6f-104">構文</span><span class="sxs-lookup"><span data-stu-id="63a6f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodProps (
    [in]  mdMethodDef md,
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,
    [in]  DWORD       dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63a6f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="63a6f-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="63a6f-106">から変更するメソッドのトークン。</span><span class="sxs-lookup"><span data-stu-id="63a6f-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="63a6f-107">からメンバー属性。</span><span class="sxs-lookup"><span data-stu-id="63a6f-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="63a6f-108">からコードのアドレス。</span><span class="sxs-lookup"><span data-stu-id="63a6f-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="63a6f-109">からメソッドの実装フラグ。</span><span class="sxs-lookup"><span data-stu-id="63a6f-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63a6f-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="63a6f-110">Requirements</span></span>  
 <span data-ttu-id="63a6f-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63a6f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63a6f-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="63a6f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="63a6f-113">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="63a6f-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63a6f-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63a6f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63a6f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="63a6f-115">See also</span></span>

- [<span data-ttu-id="63a6f-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63a6f-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="63a6f-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="63a6f-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
