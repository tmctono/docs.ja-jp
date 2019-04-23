---
title: _AxlPublicKeyBlobToPublicKeyToken 関数
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b2535441da173ee13653c68f25039fd1431261a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147434"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a><span data-ttu-id="50907-102">_AxlPublicKeyBlobToPublicKeyToken 関数</span><span class="sxs-lookup"><span data-stu-id="50907-102">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>
<span data-ttu-id="50907-103">CSP PUBLICKEYBLOB 形式から厳密な名前の公開キー トークンを算出します。</span><span class="sxs-lookup"><span data-stu-id="50907-103">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50907-104">構文</span><span class="sxs-lookup"><span data-stu-id="50907-104">Syntax</span></span>  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50907-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50907-105">Parameters</span></span>  
 `pCspPublicKeyBlob`  
 <span data-ttu-id="50907-106">[in] CSP 公開キー BLOB。</span><span class="sxs-lookup"><span data-stu-id="50907-106">[in] The CSP public key blob.</span></span>  
  
 `ppwszPublicKeyHash`  
 <span data-ttu-id="50907-107">[out] 16 進エンコードされた公開キー ハッシュを受け取るための WCHAR \* へのポインター。</span><span class="sxs-lookup"><span data-stu-id="50907-107">[out] A pointer to WCHAR \* to receive the hex-encoded public key hash.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50907-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="50907-108">Return Value</span></span>  
 <span data-ttu-id="50907-109">関数が成功した場合は `S_OK`、それ以外の場合は `S_FALSE`。</span><span class="sxs-lookup"><span data-stu-id="50907-109">`S_OK` if the function succeeds; otherwise `S_FALSE`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50907-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="50907-110">See also</span></span>

- [<span data-ttu-id="50907-111">Authenticode</span><span class="sxs-lookup"><span data-stu-id="50907-111">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
