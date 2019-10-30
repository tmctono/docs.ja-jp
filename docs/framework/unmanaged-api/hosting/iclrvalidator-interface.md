---
title: ICLRValidator インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
ms.openlocfilehash: 483d647028d1a05ea20ab836730099afe3e09374
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127846"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="d10ae-102">ICLRValidator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d10ae-102">ICLRValidator Interface</span></span>
<span data-ttu-id="d10ae-103">ポータブル実行可能 (PE) イメージを検証し、検証エラーを報告するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="d10ae-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d10ae-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="d10ae-104">Methods</span></span>  
  
|<span data-ttu-id="d10ae-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="d10ae-105">Method</span></span>|<span data-ttu-id="d10ae-106">説明</span><span class="sxs-lookup"><span data-stu-id="d10ae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d10ae-107">FormatEventInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="d10ae-107">FormatEventInfo Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="d10ae-108">指定された検証エラーに関する詳細メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="d10ae-108">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="d10ae-109">Validate メソッド</span><span class="sxs-lookup"><span data-stu-id="d10ae-109">Validate Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md)|<span data-ttu-id="d10ae-110">指定したファイル内のポータブル実行可能ファイルまたは MSIL (Microsoft 中間言語) を検証します。</span><span class="sxs-lookup"><span data-stu-id="d10ae-110">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d10ae-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="d10ae-111">Requirements</span></span>  
 <span data-ttu-id="d10ae-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10ae-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d10ae-113">**ヘッダー:** IValidator、IValidator</span><span class="sxs-lookup"><span data-stu-id="d10ae-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="d10ae-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d10ae-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d10ae-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d10ae-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d10ae-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d10ae-116">See also</span></span>

- [<span data-ttu-id="d10ae-117">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d10ae-117">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="d10ae-118">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d10ae-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="d10ae-119">CLRRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="d10ae-119">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
