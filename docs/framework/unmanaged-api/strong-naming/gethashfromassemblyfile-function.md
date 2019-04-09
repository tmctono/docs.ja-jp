---
title: GetHashFromAssemblyFile 関数
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e56a509d08b19cf449177984e7b59481eb7b09a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092163"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="8f0f0-102">GetHashFromAssemblyFile 関数</span><span class="sxs-lookup"><span data-stu-id="8f0f0-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="8f0f0-103">指定したハッシュ アルゴリズムを使用して、指定したアセンブリ ファイルのハッシュ値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="8f0f0-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="8f0f0-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="8f0f0-104">This function has been deprecated.</span></span> <span data-ttu-id="8f0f0-105">使用して、 [iclrstrongname::gethashfromassemblyfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="8f0f0-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f0f0-106">構文</span><span class="sxs-lookup"><span data-stu-id="8f0f0-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f0f0-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f0f0-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="8f0f0-108">[in]ハッシュされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="8f0f0-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="8f0f0-109">[入力、出力]ハッシュ アルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="8f0f0-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="8f0f0-110">既定のハッシュ アルゴリズムのゼロを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f0f0-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="8f0f0-111">[out]返されたハッシュ バッファー。</span><span class="sxs-lookup"><span data-stu-id="8f0f0-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="8f0f0-112">[in]要求の最大サイズの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="8f0f0-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="8f0f0-113">[out]サイズ (バイト単位) が返されますの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="8f0f0-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f0f0-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="8f0f0-114">Requirements</span></span>  
 <span data-ttu-id="8f0f0-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0f0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f0f0-116">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="8f0f0-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8f0f0-117">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8f0f0-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8f0f0-118">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="8f0f0-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f0f0-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f0f0-119">See also</span></span>

- [<span data-ttu-id="8f0f0-120">GetHashFromAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="8f0f0-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="8f0f0-121">GetHashFromAssemblyFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="8f0f0-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="8f0f0-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f0f0-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
