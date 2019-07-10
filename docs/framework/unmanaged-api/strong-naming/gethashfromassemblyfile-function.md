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
ms.openlocfilehash: 026115adc01e7dcdac3012255f0378cff6348f89
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780700"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="8ddc5-102">GetHashFromAssemblyFile 関数</span><span class="sxs-lookup"><span data-stu-id="8ddc5-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="8ddc5-103">指定したハッシュ アルゴリズムを使用して、指定したアセンブリ ファイルのハッシュ値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="8ddc5-104">この関数は非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-104">This function has been deprecated.</span></span> <span data-ttu-id="8ddc5-105">使用して、 [iclrstrongname::gethashfromassemblyfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ddc5-106">構文</span><span class="sxs-lookup"><span data-stu-id="8ddc5-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ddc5-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ddc5-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="8ddc5-108">[in]ハッシュされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="8ddc5-109">[入力、出力]ハッシュ アルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="8ddc5-110">既定のハッシュ アルゴリズムのゼロを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="8ddc5-111">[out]返されたハッシュ バッファー。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="8ddc5-112">[in]要求の最大サイズの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="8ddc5-113">[out]サイズ (バイト単位) が返されますの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ddc5-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="8ddc5-114">Requirements</span></span>  
 <span data-ttu-id="8ddc5-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ddc5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ddc5-116">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="8ddc5-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8ddc5-117">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="8ddc5-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ddc5-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ddc5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ddc5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ddc5-119">See also</span></span>

- [<span data-ttu-id="8ddc5-120">GetHashFromAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="8ddc5-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="8ddc5-121">GetHashFromAssemblyFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="8ddc5-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="8ddc5-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8ddc5-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
