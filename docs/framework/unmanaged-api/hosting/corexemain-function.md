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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7407db297a827004c851b904b2da8652778cb08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756417"
---
# <a name="corexemain-function"></a><span data-ttu-id="5759e-102">_CorExeMain 関数</span><span class="sxs-lookup"><span data-stu-id="5759e-102">_CorExeMain Function</span></span>
<span data-ttu-id="5759e-103">共通言語ランタイム (CLR) を初期化します、実行可能アセンブリの CLR ヘッダーでマネージ エントリ ポイントを検索し、実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="5759e-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5759e-104">構文</span><span class="sxs-lookup"><span data-stu-id="5759e-104">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5759e-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="5759e-105">Remarks</span></span>  
 <span data-ttu-id="5759e-106">この関数は、マネージ実行可能アセンブリから作成されたプロセスのローダーによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5759e-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="5759e-107">DLL のアセンブリ ローダーの呼び出し、 [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="5759e-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="5759e-108">オペレーティング システム ローダーでは、イメージ ファイルに指定されたエントリ ポイントに関係なく、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5759e-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="5759e-109">Windows 98、Windows ME、Windows NT、および Windows 2000 で、`_CorExeMain`オペレーティング システム ローダーのフィックス アップを関数が直接呼び出さです。</span><span class="sxs-lookup"><span data-stu-id="5759e-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="5759e-110">他のすべてのバージョンの Windows では、オペレーティング システム ローダーによって直接呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5759e-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="5759e-111">詳細については、「解説」セクションを参照してください。、 [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="5759e-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5759e-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="5759e-112">Requirements</span></span>  
 <span data-ttu-id="5759e-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5759e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5759e-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5759e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5759e-115">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="5759e-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5759e-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5759e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5759e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5759e-117">See also</span></span>

- [<span data-ttu-id="5759e-118">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="5759e-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
