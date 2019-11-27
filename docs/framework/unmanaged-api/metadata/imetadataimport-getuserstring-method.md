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
ms.openlocfilehash: 690abec6104f6eed1ad5a0eae9a6b6bb18d35b0d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436690"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="4600c-102">IMetaDataImport::GetUserString メソッド</span><span class="sxs-lookup"><span data-stu-id="4600c-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="4600c-103">指定したメタデータ トークンで表されるリテラル文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="4600c-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4600c-104">構文</span><span class="sxs-lookup"><span data-stu-id="4600c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4600c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4600c-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="4600c-106">から関連付けられている文字列を返す文字列トークン。</span><span class="sxs-lookup"><span data-stu-id="4600c-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="4600c-107">入出力要求された文字列のコピー。</span><span class="sxs-lookup"><span data-stu-id="4600c-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="4600c-108">から要求された `szString`のワイド文字単位の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="4600c-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="4600c-109">入出力返される `szString`のワイド文字単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="4600c-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4600c-110">要件</span><span class="sxs-lookup"><span data-stu-id="4600c-110">Requirements</span></span>  
 <span data-ttu-id="4600c-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4600c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4600c-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="4600c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4600c-113">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="4600c-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4600c-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4600c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4600c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4600c-115">See also</span></span>

- [<span data-ttu-id="4600c-116">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4600c-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4600c-117">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4600c-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
