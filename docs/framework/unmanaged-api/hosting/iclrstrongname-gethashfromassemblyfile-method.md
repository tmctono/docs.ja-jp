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
ms.openlocfilehash: 8131a9838cc958405ca23c75c702db5ec65a41c8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901197"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="a16dd-102">ICLRStrongName::GetHashFromAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="a16dd-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="a16dd-103">指定したハッシュ アルゴリズムを使用して、指定したアセンブリ ファイルのハッシュ値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="a16dd-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a16dd-104">構文</span><span class="sxs-lookup"><span data-stu-id="a16dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a16dd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a16dd-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="a16dd-106">からハッシュされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="a16dd-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a16dd-107">[入力、出力]ハッシュアルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="a16dd-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="a16dd-108">既定のハッシュアルゴリズムには0を使用します。</span><span class="sxs-lookup"><span data-stu-id="a16dd-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a16dd-109">入出力返されたハッシュバッファー。</span><span class="sxs-lookup"><span data-stu-id="a16dd-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a16dd-110">から要求された `pbHash`の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="a16dd-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a16dd-111">入出力`pbHash`の返されたサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="a16dd-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a16dd-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="a16dd-112">Return Value</span></span>  
 <span data-ttu-id="a16dd-113">メソッドが正常に完了した場合は `S_OK`。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](/windows/win32/seccrypto/common-hresult-values)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a16dd-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a16dd-114">要件</span><span class="sxs-lookup"><span data-stu-id="a16dd-114">Requirements</span></span>  
 <span data-ttu-id="a16dd-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a16dd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a16dd-116">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="a16dd-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a16dd-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a16dd-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a16dd-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a16dd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a16dd-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a16dd-119">See also</span></span>

- [<span data-ttu-id="a16dd-120">GetHashFromAssemblyFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="a16dd-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="a16dd-121">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a16dd-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
