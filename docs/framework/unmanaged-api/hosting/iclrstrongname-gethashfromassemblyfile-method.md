---
title: ICLRStrongName::GetHashFromAssemblyFile メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6d5ea24e40357205051188b68de8b973d2cec18
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748249"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="e1ef5-102">ICLRStrongName::GetHashFromAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="e1ef5-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="e1ef5-103">指定したハッシュ アルゴリズムを使用して、指定したアセンブリ ファイルのハッシュ値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="e1ef5-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1ef5-104">構文</span><span class="sxs-lookup"><span data-stu-id="e1ef5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1ef5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e1ef5-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="e1ef5-106">[in]ハッシュされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="e1ef5-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="e1ef5-107">[入力、出力]ハッシュ アルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="e1ef5-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="e1ef5-108">既定のハッシュ アルゴリズムのゼロを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1ef5-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="e1ef5-109">[out]返されたハッシュ バッファー。</span><span class="sxs-lookup"><span data-stu-id="e1ef5-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="e1ef5-110">[in]要求の最大サイズの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="e1ef5-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="e1ef5-111">[out]サイズ (バイト単位) が返されますの`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="e1ef5-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1ef5-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="e1ef5-112">Return Value</span></span>  
 <span data-ttu-id="e1ef5-113">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="e1ef5-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1ef5-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="e1ef5-114">Requirements</span></span>  
 <span data-ttu-id="e1ef5-115">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1ef5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1ef5-116">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e1ef5-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e1ef5-117">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="e1ef5-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1ef5-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1ef5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ef5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1ef5-119">See also</span></span>

- [<span data-ttu-id="e1ef5-120">GetHashFromAssemblyFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="e1ef5-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="e1ef5-121">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e1ef5-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
