---
title: ICLRStrongName::StrongNameGetBlob メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
ms.openlocfilehash: 9d7f1a71658b53a1b4167c767eb89c873308421b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135126"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="3b208-102">ICLRStrongName::StrongNameGetBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="3b208-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="3b208-103">指定したアドレスにある実行可能ファイルのバイナリ表現が、指定したバッファーに入れられます。</span><span class="sxs-lookup"><span data-stu-id="3b208-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b208-104">構文</span><span class="sxs-lookup"><span data-stu-id="3b208-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b208-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3b208-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="3b208-106">から読み込む実行可能ファイルへの有効なパス。</span><span class="sxs-lookup"><span data-stu-id="3b208-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="3b208-107">から実行可能ファイルの読み込み先のバッファー。</span><span class="sxs-lookup"><span data-stu-id="3b208-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="3b208-108">[入力、出力]`pbBlob`の要求された最大サイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="3b208-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="3b208-109">返されたときに、`pbBlob`の実際のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="3b208-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b208-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="3b208-110">Return Value</span></span>  
 <span data-ttu-id="3b208-111">メソッドが正常に完了した場合は `S_OK`。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](https://go.microsoft.com/fwlink/?LinkId=213878)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3b208-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b208-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="3b208-112">Requirements</span></span>  
 <span data-ttu-id="3b208-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b208-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b208-114">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="3b208-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3b208-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3b208-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b208-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b208-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b208-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b208-117">See also</span></span>

- [<span data-ttu-id="3b208-118">StrongNameGetBlobFromImage メソッド</span><span class="sxs-lookup"><span data-stu-id="3b208-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="3b208-119">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3b208-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
