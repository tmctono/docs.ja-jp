---
title: ICLRStrongName::StrongNameTokenFromAssembly メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb399b9fee5ea3e094aa9e1842a493b10eb39def
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759191"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="208c4-102">ICLRStrongName::StrongNameTokenFromAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="208c4-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="208c4-103">指定したアセンブリ ファイルから、厳密な名前トークンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="208c4-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="208c4-104">構文</span><span class="sxs-lookup"><span data-stu-id="208c4-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="208c4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="208c4-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="208c4-106">[in]アセンブリのポータブル実行可能 (PE) ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="208c4-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="208c4-107">[out]厳密な名前が返されたトークンです。</span><span class="sxs-lookup"><span data-stu-id="208c4-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="208c4-108">[out]厳密な名前トークンのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="208c4-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="208c4-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="208c4-109">Return Value</span></span>  
 <span data-ttu-id="208c4-110">`S_OK` メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="208c4-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="208c4-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="208c4-111">Remarks</span></span>  
 <span data-ttu-id="208c4-112">厳密な名前トークンは、公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="208c4-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="208c4-113">トークンは、アセンブリの署名に使用する公開キーから作成される 64 ビット ハッシュです。</span><span class="sxs-lookup"><span data-stu-id="208c4-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="208c4-114">トークンは、アセンブリの厳密な名前の一部であるし、アセンブリのメタデータから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="208c4-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="208c4-115">呼び出す必要があります、トークンが作成された後、 [iclrstrongname::strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)を割り当てられたメモリを解放するメソッド。</span><span class="sxs-lookup"><span data-stu-id="208c4-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="208c4-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="208c4-116">Requirements</span></span>  
 <span data-ttu-id="208c4-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="208c4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="208c4-118">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="208c4-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="208c4-119">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="208c4-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="208c4-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="208c4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="208c4-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="208c4-121">See also</span></span>

- [<span data-ttu-id="208c4-122">StrongNameTokenFromAssemblyEx メソッド</span><span class="sxs-lookup"><span data-stu-id="208c4-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="208c4-123">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="208c4-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
