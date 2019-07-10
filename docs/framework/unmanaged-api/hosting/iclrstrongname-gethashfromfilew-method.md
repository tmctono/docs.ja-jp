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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a5b5eb587a4739cf3481c76ef73ebc62f0a9d20
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748170"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="a2325-102">ICLRStrongName::GetHashFromFileW メソッド</span><span class="sxs-lookup"><span data-stu-id="a2325-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="a2325-103">Unicode 文字列で指定されたファイルの内容に対してハッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a2325-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2325-104">構文</span><span class="sxs-lookup"><span data-stu-id="a2325-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="a2325-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2325-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a2325-106">[in]ハッシュするファイルの Unicode の名前。</span><span class="sxs-lookup"><span data-stu-id="a2325-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a2325-107">[入力、出力]ハッシュを生成するときに使用するアルゴリズム。</span><span class="sxs-lookup"><span data-stu-id="a2325-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="a2325-108">有効なアルゴリズムを使用して、Win32 CryptoAPI で定義されています。</span><span class="sxs-lookup"><span data-stu-id="a2325-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="a2325-109">場合`piHashAlg`CALG_SHA 1 が使用される既定のアルゴリズムを 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a2325-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a2325-110">[out]生成されたハッシュを含むバイト配列。</span><span class="sxs-lookup"><span data-stu-id="a2325-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a2325-111">[in]によって示されるバッファーの最大サイズ`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="a2325-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a2325-112">[out]サイズ (バイト単位) の`pbHash`します。</span><span class="sxs-lookup"><span data-stu-id="a2325-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2325-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="a2325-113">Return Value</span></span>  
 <span data-ttu-id="a2325-114">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="a2325-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2325-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="a2325-115">Remarks</span></span>  
 <span data-ttu-id="a2325-116">このメソッドは同じ、 [iclrstrongname::gethashfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)メソッド、名前を指定する点を除いては ANSI ではなく Unicode。</span><span class="sxs-lookup"><span data-stu-id="a2325-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2325-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="a2325-117">Requirements</span></span>  
 <span data-ttu-id="a2325-118">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2325-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2325-119">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a2325-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a2325-120">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a2325-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2325-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2325-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2325-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2325-122">See also</span></span>

- [<span data-ttu-id="a2325-123">GetHashFromFile メソッド</span><span class="sxs-lookup"><span data-stu-id="a2325-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="a2325-124">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a2325-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
