<script>
  let m = 0.6334027;
  let c = 856.05180115;
  let cf = 1200;
  let at = 543;

  function updateCF() {
    if (at !== 0) {
      cf = Math.round(at * m + c);
    }
  }

  function updateAT() {
    if (cf !== 0) {
      at = Math.round((cf - c) / m);
    }
  }
</script>


<div class="w-full h-[100svh] flex">
  <div class="min-w-1/2 w-1/2 min-h-full bg-slate-100 flex justify-center items-center">
    <div class="card w-96 bg-base-100 shadow-xl min-h-[60svh] p-5 text-slate-100 flex justify-around">
        <img alt="codeforces" class="px-5 pt-5 rounded-md min-h-[25svh] object-contain" src="https://codeforces.org/s/99253/images/codeforces-sponsored-by-ton.png" />
        <div class="card-body items-center text-center">
          <h2 class="card-title">Enter your Codeforces rating!</h2>
          <p>well what if hypothetically you gave atcoder contests?</p>
        </div>
        <label class=" input input-bordered flex items-center gap-2">
          Rating
          <input bind:value={cf} on:keyup={updateAT} type="number" class="grow" placeholder="rating" />
        </label>
        <div class="pb-5"></div>
    </div>
  </div>
  <div class="min-w-1/2 w-1/2 min-h-full flex justify-center items-center">
    <div class="card w-96 bg-slate-100 shadow-xl p-5 min-h-[60svh] text-base-100 flex justify-around">
      <img alt="atcoder" class="px-5 pt-5 rounded-md  min-h-[25svh] object-contain" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQoFkSFTQjijHVJuA8lsfa5lGN5_jGNzl-F7w&s" />
      <div class="card-body items-center text-center">
        <h2 class="card-title">Enter your Atcoder rating!</h2>
        <p>well what if hypothetically you gave codeforces contests?</p>
      </div>
      <label class=" input input-bordered flex items-center gap-2 bg-slate-300">
        Rating
        <input bind:value={at} on:keyup={updateCF} type="number" class="grow" placeholder="rating" />
      </label>
      <div class="pb-5"></div>
  </div>
  </div>
</div>