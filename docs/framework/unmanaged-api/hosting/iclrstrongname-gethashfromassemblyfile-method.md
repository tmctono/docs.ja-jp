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
ms.openlocfilehash: 3fd9efd3961be1d6e6e91b881327628c598e364e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092725"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="ccf12-102">ICLRStrongName::GetHashFromAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="ccf12-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="ccf12-103">指定したハッシュ アルゴリズムを使用して、指定したアセンブリ ファイルのハッシュ値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="ccf12-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccf12-104">構文</span><span class="sxs-lookup"><span data-stu-id="ccf12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccf12-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ccf12-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="ccf12-106">からハッシュされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="ccf12-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="ccf12-107">[入力、出力]ハッシュアルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="ccf12-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="ccf12-108">既定のハッシュアルゴリズムには0を使用します。</span><span class="sxs-lookup"><span data-stu-id="ccf12-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="ccf12-109">入出力返されたハッシュバッファー。</span><span class="sxs-lookup"><span data-stu-id="ccf12-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="ccf12-110">から要求された `pbHash`の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="ccf12-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="ccf12-111">入出力`pbHash`の返されたサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="ccf12-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccf12-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="ccf12-112">Return Value</span></span>  
 <span data-ttu-id="ccf12-113">メソッドが正常に完了した場合は `S_OK`。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](https://go.microsoft.com/fwlink/?LinkId=213878)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="ccf12-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccf12-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="ccf12-114">Requirements</span></span>  
 <span data-ttu-id="ccf12-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccf12-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccf12-116">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="ccf12-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ccf12-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="ccf12-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccf12-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccf12-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf12-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccf12-119">See also</span></span>

- [<span data-ttu-id="ccf12-120">GetHashFromAssemblyFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="ccf12-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="ccf12-121">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ccf12-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
