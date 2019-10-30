---
title: _CorExeMain 関数
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
ms.openlocfilehash: 8541e7761e2f8e1839d028fdaea3eb71307ba615
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131200"
---
# <a name="_corexemain-function"></a><span data-ttu-id="d8176-102">_CorExeMain 関数</span><span class="sxs-lookup"><span data-stu-id="d8176-102">_CorExeMain Function</span></span>
<span data-ttu-id="d8176-103">共通言語ランタイム (CLR) を初期化し、実行可能アセンブリの CLR ヘッダーでマネージエントリポイントを検索して、実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="d8176-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8176-104">構文</span><span class="sxs-lookup"><span data-stu-id="d8176-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d8176-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="d8176-105">Remarks</span></span>  
 <span data-ttu-id="d8176-106">この関数は、マネージ実行可能アセンブリから作成されたプロセスでローダーによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d8176-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="d8176-107">DLL アセンブリの場合、ローダーは代わりに[Cordllmain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d8176-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="d8176-108">オペレーティングシステムローダーは、イメージファイルで指定されたエントリポイントに関係なく、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d8176-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="d8176-109">Windows 98、Windows ME、Windows NT、および Windows 2000 では、`_CorExeMain` 関数は、オペレーティングシステムローダーの修正によって間接的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d8176-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="d8176-110">それ以外のすべてのバージョンの Windows では、オペレーティングシステムローダーによって直接呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d8176-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="d8176-111">詳細につい[ては、このトピックの](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)「解説」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8176-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8176-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="d8176-112">Requirements</span></span>  
 <span data-ttu-id="d8176-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8176-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8176-114">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="d8176-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d8176-115">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d8176-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d8176-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8176-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8176-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8176-117">See also</span></span>

- [<span data-ttu-id="d8176-118">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="d8176-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
