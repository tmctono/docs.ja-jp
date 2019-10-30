---
title: ICLRStrongName::StrongNameTokenFromAssemblyEx メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
ms.openlocfilehash: 71fda266c22c4beb1e1f9c81c84d6c56a0a6110e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092586"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="c1ddc-102">ICLRStrongName::StrongNameTokenFromAssemblyEx メソッド</span><span class="sxs-lookup"><span data-stu-id="c1ddc-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="c1ddc-103">指定したアセンブリファイルから厳密な名前トークンを作成し、トークンが表す公開キーを返します。</span><span class="sxs-lookup"><span data-stu-id="c1ddc-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ddc-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1ddc-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1ddc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1ddc-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c1ddc-106">からアセンブリのポータブル実行可能 (PE) ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="c1ddc-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="c1ddc-107">入出力返された厳密な名前トークン。</span><span class="sxs-lookup"><span data-stu-id="c1ddc-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="c1ddc-108">入出力厳密な名前トークンのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="c1ddc-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="c1ddc-109">入出力返された公開キー。</span><span class="sxs-lookup"><span data-stu-id="c1ddc-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="c1ddc-110">入出力公開キーのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="c1ddc-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1ddc-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="c1ddc-111">Return Value</span></span>  
 <span data-ttu-id="c1ddc-112">メソッドが正常に完了した場合は `S_OK`。それ以外の場合は、失敗を示す HRESULT 値 (「リストの[一般的な Hresult 値](https://go.microsoft.com/fwlink/?LinkId=213878)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="c1ddc-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1ddc-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="c1ddc-113">Remarks</span></span>  
 <span data-ttu-id="c1ddc-114">厳密な名前トークンは、公開キーの短縮形です。</span><span class="sxs-lookup"><span data-stu-id="c1ddc-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="c1ddc-115">トークンは、アセンブリの署名に使用される公開キーから作成された64ビットのハッシュです。</span><span class="sxs-lookup"><span data-stu-id="c1ddc-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="c1ddc-116">トークンはアセンブリの厳密な名前の一部であり、アセンブリメタデータから読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="c1ddc-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="c1ddc-117">キーを取得してトークンを作成したら、 [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)メソッドを呼び出して、割り当てられたメモリを解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1ddc-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ddc-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="c1ddc-118">Requirements</span></span>  
 <span data-ttu-id="c1ddc-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1ddc-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ddc-120">**ヘッダー:** メタホスト .h</span><span class="sxs-lookup"><span data-stu-id="c1ddc-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c1ddc-121">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c1ddc-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1ddc-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1ddc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ddc-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1ddc-123">See also</span></span>

- [<span data-ttu-id="c1ddc-124">StrongNameTokenFromAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="c1ddc-124">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="c1ddc-125">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1ddc-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
