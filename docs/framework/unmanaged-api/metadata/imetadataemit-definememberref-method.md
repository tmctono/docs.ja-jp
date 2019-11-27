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
ms.openlocfilehash: 696389b51328e167212fb2292a873c34b9263811
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431821"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="4659a-102">IMetaDataEmit::DefineMemberRef メソッド</span><span class="sxs-lookup"><span data-stu-id="4659a-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="4659a-103">現在のスコープ外のモジュールのメンバーへの参照を定義し、その参照定義へのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="4659a-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4659a-104">構文</span><span class="sxs-lookup"><span data-stu-id="4659a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4659a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4659a-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="4659a-106">からメンバーがグローバルでない場合は、ターゲットメンバーのクラスまたはインターフェイスのトークン。メンバーがグローバルの場合は、その他のファイルの `mdModuleRef` トークンです。</span><span class="sxs-lookup"><span data-stu-id="4659a-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="4659a-107">からターゲットメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="4659a-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="4659a-108">からターゲットメンバーのシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="4659a-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="4659a-109">から`pvSigBlob`内のバイト数。</span><span class="sxs-lookup"><span data-stu-id="4659a-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="4659a-110">入出力割り当てられた `mdMemberRef` トークン。</span><span class="sxs-lookup"><span data-stu-id="4659a-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4659a-111">要件</span><span class="sxs-lookup"><span data-stu-id="4659a-111">Requirements</span></span>  
 <span data-ttu-id="4659a-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4659a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4659a-113">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="4659a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4659a-114">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="4659a-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4659a-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4659a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4659a-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4659a-116">See also</span></span>

- [<span data-ttu-id="4659a-117">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4659a-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4659a-118">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4659a-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
