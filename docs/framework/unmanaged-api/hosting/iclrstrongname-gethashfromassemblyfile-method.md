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
ms.openlocfilehash: 007de0365bf70b1f4a9a9e0f01807e7fdac19f54
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762150"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="0ee2c-102">ICLRStrongName::GetHashFromAssemblyFile メソッド</span><span class="sxs-lookup"><span data-stu-id="0ee2c-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="0ee2c-103">指定したハッシュ アルゴリズムを使用して、指定したアセンブリ ファイルのハッシュ値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="0ee2c-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ee2c-104">構文</span><span class="sxs-lookup"><span data-stu-id="0ee2c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ee2c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0ee2c-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="0ee2c-106">からハッシュされるファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="0ee2c-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="0ee2c-107">[入力、出力]ハッシュアルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="0ee2c-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="0ee2c-108">既定のハッシュアルゴリズムには0を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ee2c-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="0ee2c-109">入出力返されたハッシュバッファー。</span><span class="sxs-lookup"><span data-stu-id="0ee2c-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="0ee2c-110">から要求された最大サイズ `pbHash` 。</span><span class="sxs-lookup"><span data-stu-id="0ee2c-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="0ee2c-111">入出力の返されたサイズ (バイト単位) `pbHash` 。</span><span class="sxs-lookup"><span data-stu-id="0ee2c-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ee2c-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="0ee2c-112">Return Value</span></span>  
 <span data-ttu-id="0ee2c-113">`S_OK`メソッドが正常に完了した場合は。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](/windows/win32/seccrypto/common-hresult-values)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="0ee2c-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ee2c-114">要件</span><span class="sxs-lookup"><span data-stu-id="0ee2c-114">Requirements</span></span>  
 <span data-ttu-id="0ee2c-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ee2c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ee2c-116">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="0ee2c-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0ee2c-117">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="0ee2c-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ee2c-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ee2c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee2c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ee2c-119">See also</span></span>

- [<span data-ttu-id="0ee2c-120">GetHashFromAssemblyFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="0ee2c-120">GetHashFromAssemblyFileW Method</span></span>](iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="0ee2c-121">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0ee2c-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
