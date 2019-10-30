---
title: IValidator インターフェイス
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
ms.openlocfilehash: 1a732e59d539c330f91e8665e81dc4771b40e2d0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123286"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="6fd48-102">IValidator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fd48-102">IValidator Interface</span></span>
<span data-ttu-id="6fd48-103">ポータブル実行可能 (PE) イメージを検証し、検証エラーを報告するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="6fd48-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6fd48-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="6fd48-104">Methods</span></span>  
  
|<span data-ttu-id="6fd48-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="6fd48-105">Method</span></span>|<span data-ttu-id="6fd48-106">説明</span><span class="sxs-lookup"><span data-stu-id="6fd48-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="6fd48-107">検証</span><span class="sxs-lookup"><span data-stu-id="6fd48-107">Validate</span></span>|<span data-ttu-id="6fd48-108">指定された PE または Microsoft 中間言語 (MSIL) ファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="6fd48-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="6fd48-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="6fd48-109">FormatEventInfo</span></span>|<span data-ttu-id="6fd48-110">指定した検証エラーに対応するエラーメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="6fd48-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fd48-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="6fd48-111">Requirements</span></span>  
 <span data-ttu-id="6fd48-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fd48-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fd48-113">**ヘッダー:** IValidator、IValidator</span><span class="sxs-lookup"><span data-stu-id="6fd48-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="6fd48-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="6fd48-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fd48-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fd48-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd48-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fd48-116">See also</span></span>

- [<span data-ttu-id="6fd48-117">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6fd48-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="6fd48-118">CorRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="6fd48-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
