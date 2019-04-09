---
title: ICLRStrongName::StrongNameKeyDelete メソッド
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 412aa8fd30294ac9681a5edd02bb4bdfe25b3fab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143989"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="3ab85-102">ICLRStrongName::StrongNameKeyDelete メソッド</span><span class="sxs-lookup"><span data-stu-id="3ab85-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="3ab85-103">指定したキー コンテナーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="3ab85-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ab85-104">構文</span><span class="sxs-lookup"><span data-stu-id="3ab85-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ab85-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3ab85-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="3ab85-106">[in]削除するキー コンテナーの名前。</span><span class="sxs-lookup"><span data-stu-id="3ab85-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ab85-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="3ab85-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="3ab85-108">メソッドが正常に完了した場合それ以外の場合、エラーを示す HRESULT 値 (を参照してください[の共通 HRESULT 値](https://go.microsoft.com/fwlink/?LinkId=213878)一覧については)。</span><span class="sxs-lookup"><span data-stu-id="3ab85-108">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ab85-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="3ab85-109">Remarks</span></span>  
 <span data-ttu-id="3ab85-110">使用して、 [iclrstrongname::strongnamekeyinstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)公開/秘密キー ペアをコンテナーにインポートするメソッド。</span><span class="sxs-lookup"><span data-stu-id="3ab85-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ab85-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="3ab85-111">Requirements</span></span>  
 <span data-ttu-id="3ab85-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ab85-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ab85-113">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3ab85-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3ab85-114">**ライブラリ:** MSCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="3ab85-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3ab85-115">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3ab85-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3ab85-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ab85-116">See also</span></span>

- [<span data-ttu-id="3ab85-117">StrongNameKeyInstall メソッド</span><span class="sxs-lookup"><span data-stu-id="3ab85-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="3ab85-118">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3ab85-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
