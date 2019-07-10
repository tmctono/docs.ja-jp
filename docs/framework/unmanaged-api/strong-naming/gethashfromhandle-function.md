---
title: GetHashFromHandle 関数
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa5d5ee469d41cca46ea05fa4111ce3abff808d4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771903"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="6d9fe-102">GetHashFromHandle 関数</span><span class="sxs-lookup"><span data-stu-id="6d9fe-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="6d9fe-103">指定したハッシュ アルゴリズムを使用して、指定したファイル ハンドルを含むファイルの内容に対してハッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="6d9fe-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-104">This function has been deprecated.</span></span> <span data-ttu-id="6d9fe-105">使用して、 [iclrstrongname::gethashfromhandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d9fe-106">構文</span><span class="sxs-lookup"><span data-stu-id="6d9fe-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d9fe-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d9fe-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="6d9fe-108">[in]ハッシュされるファイルのハンドル。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="6d9fe-109">[入力、出力]ハッシュ アルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="6d9fe-110">既定のアルゴリズムに 0 を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="6d9fe-111">[out]返されたハッシュ バッファー。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="6d9fe-112">[in]要求の最大サイズの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="6d9fe-113">[out]サイズ (バイト単位)、返された`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d9fe-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="6d9fe-114">Requirements</span></span>  
 <span data-ttu-id="6d9fe-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d9fe-116">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="6d9fe-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6d9fe-117">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="6d9fe-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d9fe-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d9fe-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d9fe-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d9fe-119">See also</span></span>

- [<span data-ttu-id="6d9fe-120">GetHashFromHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="6d9fe-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="6d9fe-121">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6d9fe-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
