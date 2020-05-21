---
title: ICLRStrongName::GetHashFromFileW メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 6dbb3360132186c38c007fb5fa12a3724ca145aa
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762098"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="8d964-102">ICLRStrongName::GetHashFromFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="8d964-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="8d964-103">Unicode 文字列で指定されたファイルの内容に対してハッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8d964-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d964-104">構文</span><span class="sxs-lookup"><span data-stu-id="8d964-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="8d964-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8d964-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="8d964-106">からハッシュするファイルの Unicode 名。</span><span class="sxs-lookup"><span data-stu-id="8d964-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="8d964-107">[入力、出力]ハッシュを生成するときに使用するアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="8d964-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="8d964-108">有効なアルゴリズムは、Win32 CryptoAPI によって定義されているものです。</span><span class="sxs-lookup"><span data-stu-id="8d964-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="8d964-109">が0に設定されている場合は、 `piHashAlg` 既定のアルゴリズム CALG_SHA-1 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d964-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="8d964-110">入出力生成されたハッシュを格納しているバイト配列。</span><span class="sxs-lookup"><span data-stu-id="8d964-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="8d964-111">からが指すバッファーの最大サイズ `pbHash` 。</span><span class="sxs-lookup"><span data-stu-id="8d964-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="8d964-112">入出力のサイズ (バイト単位) `pbHash` 。</span><span class="sxs-lookup"><span data-stu-id="8d964-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d964-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="8d964-113">Return Value</span></span>  
 <span data-ttu-id="8d964-114">`S_OK`メソッドが正常に完了した場合は。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](/windows/win32/seccrypto/common-hresult-values)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8d964-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d964-115">解説</span><span class="sxs-lookup"><span data-stu-id="8d964-115">Remarks</span></span>  
 <span data-ttu-id="8d964-116">このメソッドは[ICLRStrongName:: GetHashFromFile](iclrstrongname-gethashfromfile-method.md)メソッドと同じですが、ファイル名の指定は ANSI ではなく Unicode である点が異なります。</span><span class="sxs-lookup"><span data-stu-id="8d964-116">This method is the same as the [ICLRStrongName::GetHashFromFile](iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d964-117">要件</span><span class="sxs-lookup"><span data-stu-id="8d964-117">Requirements</span></span>  
 <span data-ttu-id="8d964-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d964-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d964-119">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="8d964-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8d964-120">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="8d964-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d964-121">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d964-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d964-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d964-122">See also</span></span>

- [<span data-ttu-id="8d964-123">GetHashFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="8d964-123">GetHashFromFile Method</span></span>](iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="8d964-124">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8d964-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
