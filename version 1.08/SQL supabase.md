CREATE TABLE athlete_memory (
  athlete_id text NOT NULL,
  fact_key   text NOT NULL,
  fact_value text NOT NULL,
  updated_at timestamptz NOT NULL DEFAULT now(),
  PRIMARY KEY (athlete_id, fact_key)
);
CREATE TABLE chat_history (
  id         bigserial PRIMARY KEY,
  athlete_id text NOT NULL,
  role       text NOT NULL,
  content    text NOT NULL,
  created_at timestamptz NOT NULL DEFAULT now()
);
create table wearable_samples (
  id bigint generated always as identity primary key,
  athlete_id text, source text not null, metric text not null,
  value numeric, unit text, details text,
  period_start timestamptz, recorded_at timestamptz not null,
  created_at timestamptz not null default now()
);
