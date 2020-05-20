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
ms.openlocfilehash: 6fd7a19d9fc77b43bbceb1b5e5399a455429e700
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616152"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="05531-102">FExecuteInAppDomainCallback 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="05531-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="05531-103">マネージコードを実行するために共通言語ランタイム (CLR) によって呼び出される関数を指します。</span><span class="sxs-lookup"><span data-stu-id="05531-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="05531-104">この関数ポインターは .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="05531-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05531-105">構文</span><span class="sxs-lookup"><span data-stu-id="05531-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05531-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="05531-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="05531-107">から実行されるマネージコードを含む、非透過的な呼び出し元割り当てメモリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="05531-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="05531-108">このメモリの割り当てと有効期間は、呼び出し元 (つまり CLR) によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="05531-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="05531-109">これは CLR マネージヒープメモリではありません。</span><span class="sxs-lookup"><span data-stu-id="05531-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05531-110">要件</span><span class="sxs-lookup"><span data-stu-id="05531-110">Requirements</span></span>  
 <span data-ttu-id="05531-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05531-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05531-112">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="05531-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05531-113">**ライブラリ:** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="05531-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="05531-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05531-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05531-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="05531-115">See also</span></span>

- [<span data-ttu-id="05531-116">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="05531-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
