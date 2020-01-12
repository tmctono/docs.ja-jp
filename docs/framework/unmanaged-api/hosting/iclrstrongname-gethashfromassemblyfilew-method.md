---
title: ICLRStrongName::GetHashFromAssemblyFileW メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: d98181e0d43206bfbf96182d7e4acf33da486348
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901173"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="3e9e4-102">ICLRStrongName::GetHashFromAssemblyFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="3e9e4-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="3e9e4-103">Unicode 文字列で指定されたファイルの内容に対してハッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3e9e4-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e9e4-104">構文</span><span class="sxs-lookup"><span data-stu-id="3e9e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e9e4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e9e4-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="3e9e4-106">からハッシュされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="3e9e4-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="3e9e4-107">このパラメーターは Unicode 文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e9e4-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="3e9e4-108">[入力、出力]ハッシュアルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="3e9e4-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="3e9e4-109">既定のハッシュアルゴリズムには0を使用します。</span><span class="sxs-lookup"><span data-stu-id="3e9e4-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="3e9e4-110">入出力返されたハッシュバッファー。</span><span class="sxs-lookup"><span data-stu-id="3e9e4-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="3e9e4-111">から要求された `pbHash`の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="3e9e4-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="3e9e4-112">入出力`pbHash`の返されたサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="3e9e4-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e9e4-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="3e9e4-113">Return Value</span></span>  
 <span data-ttu-id="3e9e4-114">メソッドが正常に完了した場合は `S_OK`。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](/windows/win32/seccrypto/common-hresult-values)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3e9e4-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e9e4-115">要件</span><span class="sxs-lookup"><span data-stu-id="3e9e4-115">Requirements</span></span>  
 <span data-ttu-id="3e9e4-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e9e4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e9e4-117">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="3e9e4-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3e9e4-118">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3e9e4-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e9e4-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e9e4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e9e4-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e9e4-120">See also</span></span>

- [<span data-ttu-id="3e9e4-121">GetHashFromAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="3e9e4-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="3e9e4-122">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3e9e4-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
