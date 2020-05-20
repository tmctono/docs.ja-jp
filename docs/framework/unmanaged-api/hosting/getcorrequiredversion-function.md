---
title: GetCORRequiredVersion 関数
ms.date: 03/30/2017
api_name:
- GetCORRequiredVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetCORRequiredVersion
helpviewer_keywords:
- GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type:
- apiref
ms.openlocfilehash: 6b9fd62102056a8d5f859ac913f4786f04c1df7e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617244"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="08e32-102">GetCORRequiredVersion 関数</span><span class="sxs-lookup"><span data-stu-id="08e32-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="08e32-103">必要な共通言語ランタイム (CLR) のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="08e32-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="08e32-104">この関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="08e32-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08e32-105">構文</span><span class="sxs-lookup"><span data-stu-id="08e32-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08e32-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="08e32-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="08e32-107">入出力バージョン番号を指定する文字列を格納しているバッファー。</span><span class="sxs-lookup"><span data-stu-id="08e32-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="08e32-108">からバッファーのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="08e32-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="08e32-109">入出力バッファーで返されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="08e32-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08e32-110">要件</span><span class="sxs-lookup"><span data-stu-id="08e32-110">Requirements</span></span>  
 <span data-ttu-id="08e32-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08e32-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08e32-112">**ヘッダー:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="08e32-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08e32-113">**ライブラリ:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="08e32-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08e32-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08e32-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e32-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="08e32-115">See also</span></span>

- [<span data-ttu-id="08e32-116">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="08e32-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
