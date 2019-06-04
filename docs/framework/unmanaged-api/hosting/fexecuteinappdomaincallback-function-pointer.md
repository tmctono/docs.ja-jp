---
title: FExecuteInAppDomainCallback 関数ポインター
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26b3de456bc28f51cb20ab72b3934041ec6b06ae
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490442"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="a01da-102">FExecuteInAppDomainCallback 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="a01da-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="a01da-103">マネージ コードを実行する共通言語ランタイム (CLR) によって呼び出される関数を指します。</span><span class="sxs-lookup"><span data-stu-id="a01da-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="a01da-104">この関数ポインターは、.NET Framework 4 では廃止されました。</span><span class="sxs-lookup"><span data-stu-id="a01da-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a01da-105">構文</span><span class="sxs-lookup"><span data-stu-id="a01da-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a01da-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a01da-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="a01da-107">[in]実行されるマネージ コードを含む非透過の呼び出し元が割り当てたメモリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a01da-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="a01da-108">割り当てとメモリの有効期間は、呼び出し元の (つまり、CLR) によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="a01da-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="a01da-109">これは、CLR のマネージ ヒープ メモリではありません。</span><span class="sxs-lookup"><span data-stu-id="a01da-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a01da-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="a01da-110">Requirements</span></span>  
 <span data-ttu-id="a01da-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a01da-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a01da-112">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a01da-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a01da-113">**ライブラリ:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="a01da-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="a01da-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a01da-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a01da-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a01da-115">See also</span></span>

- [<span data-ttu-id="a01da-116">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="a01da-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
