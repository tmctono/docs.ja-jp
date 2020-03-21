---
title: IMetaDataEmit2::SaveDelta メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
ms.openlocfilehash: 0ebcab7a759b64bfbb254df1c1aa339cde77d054
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175565"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="c4868-102">IMetaDataEmit2::SaveDelta メソッド</span><span class="sxs-lookup"><span data-stu-id="c4868-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="c4868-103">現在のエディット コンティニュ セッションの変更を、指定したファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="c4868-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4868-104">構文</span><span class="sxs-lookup"><span data-stu-id="c4868-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4868-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c4868-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="c4868-106">[in]変更を保存するファイル名。</span><span class="sxs-lookup"><span data-stu-id="c4868-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="c4868-107">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="c4868-107">[in] Reserved.</span></span> <span data-ttu-id="c4868-108">ゼロを指定してください。</span><span class="sxs-lookup"><span data-stu-id="c4868-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4868-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c4868-109">Requirements</span></span>  
 <span data-ttu-id="c4868-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4868-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4868-111">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="c4868-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4868-112">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4868-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4868-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4868-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4868-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4868-114">See also</span></span>

- [<span data-ttu-id="c4868-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c4868-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="c4868-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c4868-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
