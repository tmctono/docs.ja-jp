---
title: ICLRStrongName::StrongNameSignatureSize メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
ms.openlocfilehash: e789996af3aedd17251fc52cde52a336f65053ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176345"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="51bd6-102">ICLRStrongName::StrongNameSignatureSize メソッド</span><span class="sxs-lookup"><span data-stu-id="51bd6-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="51bd6-103">厳密な名前の署名のサイズが返されます。</span><span class="sxs-lookup"><span data-stu-id="51bd6-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="51bd6-104">このメソッドは、通常、遅延署名されたアセンブリを作成するときに、ファイルに確保する領域を決定するためにコンパイラによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="51bd6-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51bd6-105">構文</span><span class="sxs-lookup"><span data-stu-id="51bd6-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="51bd6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="51bd6-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="51bd6-107">[in]厳密な名前の署名を生成するために使用されるキー ペアのパブリック部分を含む[、型の PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)の構造体。</span><span class="sxs-lookup"><span data-stu-id="51bd6-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="51bd6-108">[in]のサイズ (バイト単位)`pbPublicKeyBlob`です。</span><span class="sxs-lookup"><span data-stu-id="51bd6-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="51bd6-109">[in]厳密な名前の署名を格納するために必要なバイト数。</span><span class="sxs-lookup"><span data-stu-id="51bd6-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51bd6-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="51bd6-110">Return Value</span></span>  
 <span data-ttu-id="51bd6-111">`S_OK`メソッドが正常に完了した場合。それ以外の場合は、失敗を示す HRESULT 値です (リストの[HRESULT の共通値](/windows/win32/seccrypto/common-hresult-values)を参照)。</span><span class="sxs-lookup"><span data-stu-id="51bd6-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51bd6-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="51bd6-112">Requirements</span></span>  
 <span data-ttu-id="51bd6-113">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51bd6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51bd6-114">**ヘッダー:** メタホスト.h</span><span class="sxs-lookup"><span data-stu-id="51bd6-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="51bd6-115">**ライブラリ:** MSCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="51bd6-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51bd6-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51bd6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51bd6-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="51bd6-117">See also</span></span>

- [<span data-ttu-id="51bd6-118">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="51bd6-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
