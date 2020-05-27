---
title: IMetaDataEmit::DefineMemberRef メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
ms.openlocfilehash: 576f4561ed782f091840ac378831110a1bfef9c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004695"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="e2ebe-102">IMetaDataEmit::DefineMemberRef メソッド</span><span class="sxs-lookup"><span data-stu-id="e2ebe-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="e2ebe-103">現在のスコープ外のモジュールのメンバーへの参照を定義し、その参照定義へのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="e2ebe-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ebe-104">構文</span><span class="sxs-lookup"><span data-stu-id="e2ebe-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2ebe-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e2ebe-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="e2ebe-106">からメンバーがグローバルでない場合は、ターゲットメンバーのクラスまたはインターフェイスのトークン。メンバーがグローバルの場合は、 `mdModuleRef` その他のファイルのトークン。</span><span class="sxs-lookup"><span data-stu-id="e2ebe-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="e2ebe-107">からターゲットメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="e2ebe-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e2ebe-108">からターゲットメンバーのシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="e2ebe-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="e2ebe-109">からのバイト数 `pvSigBlob` 。</span><span class="sxs-lookup"><span data-stu-id="e2ebe-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="e2ebe-110">入出力`mdMemberRef`割り当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="e2ebe-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2ebe-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="e2ebe-111">Requirements</span></span>  
 <span data-ttu-id="e2ebe-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2ebe-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2ebe-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="e2ebe-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e2ebe-114">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2ebe-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2ebe-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2ebe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ebe-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2ebe-116">See also</span></span>

- [<span data-ttu-id="e2ebe-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2ebe-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e2ebe-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e2ebe-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
