---
title: IMetaDataImport::GetUserString メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type:
- apiref
ms.openlocfilehash: 358ca84f32e1b233116605bf5486cc9a01b42e67
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503506"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="cbd9d-102">IMetaDataImport::GetUserString メソッド</span><span class="sxs-lookup"><span data-stu-id="cbd9d-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="cbd9d-103">指定したメタデータ トークンで表されるリテラル文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="cbd9d-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbd9d-104">構文</span><span class="sxs-lookup"><span data-stu-id="cbd9d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbd9d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cbd9d-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="cbd9d-106">から関連付けられている文字列を返す文字列トークン。</span><span class="sxs-lookup"><span data-stu-id="cbd9d-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="cbd9d-107">入出力要求された文字列のコピー。</span><span class="sxs-lookup"><span data-stu-id="cbd9d-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="cbd9d-108">から要求されたのワイド文字単位の最大サイズ `szString` 。</span><span class="sxs-lookup"><span data-stu-id="cbd9d-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="cbd9d-109">入出力返されたのワイド文字のサイズ `szString` 。</span><span class="sxs-lookup"><span data-stu-id="cbd9d-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbd9d-110">要件</span><span class="sxs-lookup"><span data-stu-id="cbd9d-110">Requirements</span></span>  
 <span data-ttu-id="cbd9d-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbd9d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbd9d-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="cbd9d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbd9d-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="cbd9d-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cbd9d-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbd9d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd9d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbd9d-115">See also</span></span>

- [<span data-ttu-id="cbd9d-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbd9d-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="cbd9d-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cbd9d-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
