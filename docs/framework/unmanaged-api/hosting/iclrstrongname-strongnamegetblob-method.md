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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbc0262062eddb363b0a00535a2d099100124b67
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748080"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="a86ae-102">ICLRStrongName::StrongNameGetBlob メソッド</span><span class="sxs-lookup"><span data-stu-id="a86ae-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="a86ae-103">指定したアドレスにある実行可能ファイルのバイナリ表現が、指定したバッファーに入れられます。</span><span class="sxs-lookup"><span data-stu-id="a86ae-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a86ae-104">構文</span><span class="sxs-lookup"><span data-stu-id="a86ae-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a86ae-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a86ae-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a86ae-106">[in]読み込まれる実行可能ファイルへの有効なパス。</span><span class="sxs-lookup"><span data-stu-id="a86ae-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="a86ae-107">[in]実行可能ファイルを読み込むバッファー。</span><span class="sxs-lookup"><span data-stu-id="a86ae-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="a86ae-108">[入力、出力]最大サイズ (バイト単位) を要求された`pbBlob`します。</span><span class="sxs-lookup"><span data-stu-id="a86ae-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="a86ae-109">関数が戻るとき、実際のサイズをバイト単位の`pbBlob`します。</span><span class="sxs-lookup"><span data-stu-id="a86ae-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a86ae-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="a86ae-110">Return Value</span></span>  
 <span data-ttu-id="a86ae-111">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="a86ae-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a86ae-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a86ae-112">Requirements</span></span>  
 <span data-ttu-id="a86ae-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a86ae-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a86ae-114">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a86ae-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a86ae-115">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a86ae-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a86ae-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a86ae-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a86ae-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a86ae-117">See also</span></span>

- [<span data-ttu-id="a86ae-118">StrongNameGetBlobFromImage メソッド</span><span class="sxs-lookup"><span data-stu-id="a86ae-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="a86ae-119">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a86ae-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
