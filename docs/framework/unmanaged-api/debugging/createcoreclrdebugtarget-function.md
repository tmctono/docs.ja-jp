---
title: CreateCoreClrDebugTarget 関数
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
ms.openlocfilehash: 0b210f105495fa3f5595adbcb0805e1d1fb62310
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179216"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="deb88-102">CreateCoreClrDebugTarget 関数</span><span class="sxs-lookup"><span data-stu-id="deb88-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="deb88-103">リモート コンピューターで実行されているデバッガー プロキシへの接続を作成し、リモート コンピューター上で実行中のプロセスと読み込まれたランタイムを照会するために使用できる[ICoreClrDebugTarget](icoreclrdebugtarget-interface.md)オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="deb88-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="deb88-104">構文</span><span class="sxs-lookup"><span data-stu-id="deb88-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="deb88-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="deb88-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="deb88-106">[in] リモート対象コンピューターの IPv4 アドレス。</span><span class="sxs-lookup"><span data-stu-id="deb88-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="deb88-107">[アウト]作成される[オブジェクト](icoreclrdebugtarget-interface.md)へのポインター。</span><span class="sxs-lookup"><span data-stu-id="deb88-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="deb88-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="deb88-108">Return Value</span></span>  
 <span data-ttu-id="deb88-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="deb88-109">S_OK</span></span>  
 <span data-ttu-id="deb88-110">プロセス内の CLR 数が正常に判別され、対応するハンドルとパスの配列が正しく入力されました。</span><span class="sxs-lookup"><span data-stu-id="deb88-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="deb88-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="deb88-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="deb88-112">`ppTarget`  用に十分なメモリを割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="deb88-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="deb88-113">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="deb88-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="deb88-114">その他のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="deb88-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deb88-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="deb88-115">Requirements</span></span>  
 <span data-ttu-id="deb88-116">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="deb88-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deb88-117">**ヘッダー:** インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="deb88-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="deb88-118">**ライブラリ:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="deb88-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="deb88-119">**.NET フレームワークのバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="deb88-119">**.NET Framework Versions:** 3.5 SP1</span></span>
