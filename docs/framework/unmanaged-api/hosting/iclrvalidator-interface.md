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
ms.openlocfilehash: e071f9cba7e991c59bf697647e0e4badea57573a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762046"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="9566c-102">ICLRValidator インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9566c-102">ICLRValidator Interface</span></span>
<span data-ttu-id="9566c-103">ポータブル実行可能 (PE) イメージを検証し、検証エラーを報告するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="9566c-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9566c-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9566c-104">Methods</span></span>  
  
|<span data-ttu-id="9566c-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9566c-105">Method</span></span>|<span data-ttu-id="9566c-106">説明</span><span class="sxs-lookup"><span data-stu-id="9566c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9566c-107">FormatEventInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="9566c-107">FormatEventInfo Method</span></span>](iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="9566c-108">指定された検証エラーに関する詳細メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="9566c-108">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="9566c-109">Validate メソッド</span><span class="sxs-lookup"><span data-stu-id="9566c-109">Validate Method</span></span>](iclrvalidator-validate-method.md)|<span data-ttu-id="9566c-110">指定したファイル内のポータブル実行可能ファイルまたは MSIL (Microsoft 中間言語) を検証します。</span><span class="sxs-lookup"><span data-stu-id="9566c-110">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9566c-111">要件</span><span class="sxs-lookup"><span data-stu-id="9566c-111">Requirements</span></span>  
 <span data-ttu-id="9566c-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9566c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9566c-113">**ヘッダー:** IValidator、IValidator</span><span class="sxs-lookup"><span data-stu-id="9566c-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="9566c-114">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="9566c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9566c-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9566c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9566c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9566c-116">See also</span></span>

- [<span data-ttu-id="9566c-117">ICLRErrorReportingManager インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9566c-117">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="9566c-118">ホスト インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9566c-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="9566c-119">CLRRuntimeHost コクラス</span><span class="sxs-lookup"><span data-stu-id="9566c-119">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
